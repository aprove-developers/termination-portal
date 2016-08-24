---
title: Java Bytecode
permalink: /Java_Bytecode/
---

This page is to record the current status of the Java Bytecode (JBC) Category of the Termination Competition. (Discussion should take place on the termtools mailing list.)

Java vs. Java Bytecode
----------------------

Every Java problem can be compiled into an equivalent Java Bytecode problem. For technical reasons, the current tools only work on this compiled version of the original program. However, the result of the analysis also gives information about the termination behaviour of the original Java program.

Every JBC problem that resulted out of Java source code should include this source in addition to the compiled class files. This way we can communicate that we are interested in termination analysis of a real imperative programming language.

As discussed in the steering committee, the compilation of a JBC problem based on given Java code is done manually, so the existing tools do not have to implement or use a Java compiler.

There are languages different from Java that compile to JBC (e.g. Python/Jython, Ruby/JRuby, Scala, ...). The JBC category can be filled with corresponding problems. Here, too, the source files used to generate the JBC code should be provided.

Problem definition
------------------

A JBC problem is defined by up to three parts.

-   byte code
-   source
-   start method

### Code

Providing the code is straightforward and is accomplished using a [.jar file](http://en.wikipedia.org/wiki/JAR_(file_format)) that contains all .class files needed for the analysis.

### Java Source

This part is optional. If the source for the compiled program is available, the corresponding source files are packed into a file **source.zip** which is then stored in the .jar file.

### Start Method

Analysis starts with **public static void main(String[] args)**. This method is specified in the .jar file by adding a file **META-INF/MANIFEST.MF** including a line **Main-Class: some/package/SomeClass**. Note that it is unclear whether the standard is slashed or dotted notation, so it may be a good idea to accept both.

Using constructs like **args.length** or **args[i].length()** one gets unknown non-negative **int** values and can use these to create a large number of problem instances. As an example, the following code can be used to construct problems where termination of some algorithm working on lists of arbitrary length should be proved.

`public static void main(String[] args) {`
`  // create list of given length`
`  List list = new List(args.length);`
`                   `
`  // work on the created list`
`  doSomething(list);`
`}`

Participants
------------

In the 2009 competition the tools [Julia](/Tools:Julia "wikilink"), [COSTA](http://costa.ls.fi.upm.es/costa/costa.php) and [AProVE](/Tools:AProVE "wikilink") took part in the JBC categories.

Details
-------

### Version

The bytecode major version must be 50 (Java 6) or lower. Version 51 (Java 7) is not allowed.

### Errors and Exceptions

In most cases, an instance of **java.lang.Error** thrown by the JVM is undesired behaviour. If an example problem triggers this, we should consider this example as broken and not use it in the competition.

### Considered Types

Exactly the types provided in the .jar file are considered, with a few additions needed for basic examples.

The list of considered classes can be extended in the future to allow for more advanced examples, e.g. involving **System.out.println(...)** and other "library" code.

All additional class files are taken from a Debian version of OpenJDK [1].

The class **java.lang.String** needs to be considered. Especially the method **String.length()I** is useful to construct problem instances out of the argument array of the initial method (**String[] args**).

To be able to initialize **java.lang.String**, we also need the classes **java.lang.String\$CaseInsensitiveComparator**, **java.util.Comparator**, and **java.io.ObjectStreamField**.

Furthermore, usage of all the exceptions/errors mentioned in the JVMS is allowed (all in **java.lang.\***):

-   AbstractMethodError
-   ArithmeticException
-   ArrayIndexOutOfBoundsException
-   ArrayStoreException
-   ClassCastException
-   IllegalAccessError
-   IncompatibleClassChangeError
-   NegativeArraySizeException
-   NoClassDefFoundError
-   NoSuchFieldError
-   NoSuchMethodError
-   NullPointerException

Because all array types implement **java.lang.Cloneable** and **java.io.Serializable**, these interfaces must also be allowed.

The following types are part of the hierarchy of a type mentioned before, so they must be included (all in **java.lang.\***):

-   CharSequence
-   Comparable
-   Error
-   Exception
-   IndexOutOfBoundsException
-   LinkageError
-   Object
-   RuntimeException
-   Throwable

#### Native Methods

To initialize **Object**, we need to implement the native method **Object.registerNatives()V**. This method is implemented "no-op". To actually throw instances of **Exception** (or **Throwable** in general), the native method **Throwable.fillInStackTrace()V** needs to be implemented. This method, too, is implemented as "no-op".

The remaining native methods are not considered (all in **java.lang.\***):

-   Object.clone()Ljava/lang/Object;
-   Object.getClass()Ljava/lang/Class;
-   Object.hashCode()I
-   Object.notifyAll()V
-   Object.notify()V
-   Object.wait(J)
-   String.intern()Ljava/lang/String;

#### Example

As an example, examples calling **java.lang.Object.equals(Ljava/lang/Object;)Z** are allowed, but the method **java.lang.Object.toString()Ljava/lang/String;** may not be called because the class **java.lang.StringBuilder** is unknown.

#### Included Files

-   java/io/ObjectStreamField.class
-   java/io/Serializable.class
-   java/lang/AbstractMethodError.class
-   java/lang/ArithmeticException.class
-   java/lang/ArrayIndexOutOfBoundsException.class
-   java/lang/ArrayStoreException.class
-   java/lang/CharSequence.class
-   java/lang/ClassCastException.class
-   java/lang/Cloneable.class
-   java/lang/Comparable.class
-   java/lang/Error.class
-   java/lang/Exception.class
-   java/lang/IllegalAccessError.class
-   java/lang/IncompatibleClassChangeError.class
-   java/lang/IndexOutOfBoundsException.class
-   java/lang/LinkageError.class
-   java/lang/NegativeArraySizeException.class
-   java/lang/NoClassDefFoundError.class
-   java/lang/NoSuchFieldError.class
-   java/lang/NoSuchMethodError.class
-   java/lang/NullPointerException.class
-   java/lang/Object.class
-   java/lang/RuntimeException.class
-   java/lang/String\$CaseInsensitiveComparator.class
-   java/lang/String.class
-   java/lang/Throwable.class
-   java/util/Comparator.class

[1]: rt.jar in:

`    openjdk-6-jre-headless_6b11-9.1+lenny2_amd64.deb:`
`    `[`http://packages.debian.org/lenny/amd64/openjdk-6-jre-headless/download`](http://packages.debian.org/lenny/amd64/openjdk-6-jre-headless/download)
`    Exact Size  22423776 Byte (21.4 MByte)`
`    MD5 checksum  645caac427ee007eed470895fc12ab9e`
`    SHA1 checksum   f2cbf934681503b648f7dceb662e086a3bda5767`
`    SHA256 checksum 349a2a500d01574906d96ca7a8ee2486415d1aba5bf2c3e4c0cc2fe8a5c00efd`

### Opcodes

All opcodes are allowed, with the following exceptions.

-   The opcodes **LDC (0x12)** and **LDC_W (0x13)** are not allowed in the variants that return a **String** or **Class** instance. These variants are problematic, because they may return some already known instance.
-   The opcode **INVOKEDYNAMIC (0xBA)** is not part of the instruction set of Java 6, so it is not allowed.
-   The opcodes **MONITORENTER (0xC2)** and **MONITOREXIT (0xC3)** only make sense when using multithreading. Furthermore, correct handling of **MONITOREXIT** is more involved. As a result, these two opcodes are not allowed.
-   The reserved opcodes **BREAKPOINT (0xCA)**, **IMPDEP1 (0xFE)**, **IMPDEP2 (0xFF)** are not allowed.

### Overflows

Integer overflows and related problems are not handled. This means proving termination of the following Java program snippet is not considered to be wrong.

`int i = 0;`
`while (i <= 2147483647) {`
`  i++;`
`}`

### Categories

The JBC problems are divided into two categories. One category contains all examples that make use of recursion, whereas all examples in the other category do not use recursion at all.

The reason is that recursion poses a special problem for the analysis since one has to handle the call stack properly. We think that it is interesting to evaluate the performance of termination analyzers separately for programs with and without recursion.

### Verification

All input problems must pass the bytecode verification process. Therefore, the analyzers do not need to verify the given bytecode.

[Category:Categories](/Category:Categories "wikilink")
