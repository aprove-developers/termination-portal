---
title: C Integer Programs
permalink: /C_Integer_Programs/
---

[Category:Categories](/Category:Categories "wikilink")

Proposal
--------

For the Termination Competition 2015, we introduce a new category for C programs restricted to a very small subset of C operating only on integers with addition, subtraction, and multiplication. The purpose of this category is twofold: First, it is easier for new participants to first start with a restricted subset of C than directly tackling the whole language. Second, this subset captures all necessary concepts to express integer transition systems as used by many program analysis tools as intermediate representation of programs.

Syntax and Semantics
--------------------

The syntax of termination problems in this category is defined using the following ANTLR grammar, which can also be used to automatically build a parser:

`/*   Type:        ANTLR`
` *   Title:       Grammar for C Integer Programs`
` *   Description: A grammar definiton for C integer programs`
` *   Project:     AProVE`
` *   Authors:     Thomas Ströder`
` *   Copyright:   Copyright (c) 2015`
` *   Department:  RWTH Aachen / Templergraben 55 / D-52056 Aachen`
` *`
` * The following license text is based on the "BSD licence".`
` *`
` * Redistribution and use in source and binary forms, with or without`
` * modification, are permitted provided that the following conditions`
` * are met:`
` * 1. Redistributions of source code must retain the above copyright`
` *    notice, this list of conditions and the following disclaimer.`
` * 2. Redistributions in binary form must reproduce the above copyright`
` *    notice, this list of conditions and the following disclaimer in the`
` *    documentation and/or other materials provided with the distribution.`
` * 3. The name of the author may not be used to endorse or promote products`
` *    derived from this software without specific prior written permission.`
` *`
```  * THIS SOFTWARE IS PROVIDED BY THE AUTHOR ``AS IS'' AND ANY EXPRESS OR ```
` * IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES`
` * OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED.`
` * IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY DIRECT, INDIRECT,`
` * INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT`
` * NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,`
` * DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY`
` * THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT`
` * (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF`
` * THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.`
` */`
`grammar IntProg;`
`// parser rules`
`nondet : NONDETNAME W* OPENP W* CLOSEP;`
`num_atom : ZERO | POS | nondet | V | OPENP W* bool_expr W* CLOSEP;`
`mult_expr : num_atom (W* MULT W* num_atom)*;`
`num_expr : mult_expr (W* (PLUS | MINUS) W* mult_expr)* | MINUS W* mult_expr (W* (PLUS | MINUS) W* mult_expr)*;`
`bool_atom : TRUE | FALSE | num_expr (W* BO W* num_expr)?;`
`and_expr : bool_atom (W* AND W* bool_atom)*;`
`bool_expr : and_expr (W* OR W* and_expr)* | NOT W* bool_atom;`
`loop : WHILE W* OPENP W* bool_expr W* CLOSEP W* OPENC W* (instructions W*)? CLOSEC;`
`condition :`
`    IF`
`    W*`
`    OPENP W* bool_expr W* CLOSEP`
`    W*`
`    OPENC W* (instructions W*)? CLOSEC`
`    (W* ELSE W* OPENC W* (instructions W*)? CLOSEC)?;`
`assignment : V W* ASSIGN W* num_expr W* TERMINATOR;`
`instruction : loop | condition | assignment;`
`declaration : INT W+ V (W* COMMA W* V)* W* TERMINATOR;`
`declarations : declaration (W* declarations)?;`
`instructions : instruction (W* instructions)?;`
`// the opening part of each program `
`// ("typedef enum {false,true} bool;extern int __VERIFIER_nondet_int(void);int main(){")`
`pre :`
`    W*`
`    TYPEDEF W+ ENUM W* OPENC W* FALSE W* COMMA W* TRUE W* CLOSEC W* BOOL W* TERMINATOR`
`    W*`
`    EXTERN W+ INT W+ NONDETNAME W* OPENP W* VOID W* CLOSEP W* TERMINATOR`
`    W*`
`    INT W+ MAIN W* OPENP W* CLOSEP W* OPENC;`
`// the closing part of each program ("return 0;}")`
`post : RETURN W+ ZERO W* TERMINATOR W* CLOSEC W*;`
`program : pre (W* declarations)? (W* instructions)? W* post;`
`// lexer rules`
`INT : 'int';`
`IF : 'if';`
`WHILE : 'while';`
`ELSE : 'else';`
`TERMINATOR : ';';`
`OPENP : '(';`
`CLOSEP : ')';`
`OPENC : '{';`
`CLOSEC : '}';`
`MULT : '*';`
`MINUS : '-';`
`PLUS : '+';`
`BO : '<=' | '>=' | '<' | '>' | '==' | '!=';`
`ASSIGN : '=';`
`NONDETNAME : '__VERIFIER_nondet_int';`
`OR : '||';`
`AND : '&&';`
`NOT : '!';`
`TRUE : 'true';`
`FALSE : 'false';`
`TYPEDEF : 'typedef';`
`ENUM : 'enum';`
`COMMA : ',';`
`BOOL : 'bool';`
`EXTERN : 'extern';`
`VOID : 'void';`
`MAIN : 'main';`
`RETURN : 'return';`
`ZERO : '0';`
`POSITIVE : NONZERO DIGIT*;`
`fragment NONZERO : '1'..'9';`
`fragment DIGIT : ZERO | NONZERO;`
`V : CHAR ALPHANUM*;`
`fragment ALPHANUM : CHAR | DIGIT;`
`fragment CHAR : LOW | UP;`
`fragment LOW : 'a'..'z';`
`fragment UP: 'A'..'Z';`
`W : ' ' | '\n' | '\r' | '\t';`
`BLOCKCOMMENT : '/*' (.)* '*/' {$channel=HIDDEN;};`
`LINECOMMENT : '//' (~('\r'|'\n'))* {$channel=HIDDEN;};`

Calls to `__VERIFIER_nondet_int()` yield non-deterministic values (possibly different ones each time the function is called) and each function call terminates without side effects.

Integers are treated as mathematical integers (so no overflows can occur) and apart from that, the C-sematics is used. So while the grammar above allows, e.g., nesting of boolean expressions inside arithmetic expressions (to make the automated generation of a parser easier), such programs have no defined semantics and are excluded from benchmarks for the competition.
