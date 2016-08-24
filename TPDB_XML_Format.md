---
title: TPDB XML Format
permalink: /TPDB_XML_Format/
---

A proposal for an XML grammar for termination problems
------------------------------------------------------

Still needs to be formalised and completed.

    <code>
    <tp version="1.0">
        <meta>
            <author/>
            <date/>
            <originalcomment/>
        </meta>
        <termination>
            <theory><theorydecl>Multiple</theorydecl></theory>
            <strategy>
                <INNERMOST/> |
                <OUTERMOST/> |
                <CONTEXTSENSITIVE>
                    <contextsensitivestuff/>
                </CONTEXTSENSITIVE>
                |<NONE/>
            </strategy>
            <conditional type="ltr|join"/>
            <type>TRS|SRS</type>
            <status>TERMINATES|DOESNTERMINATE|DUNNO</status>
        </termination>
        <rules>
            <rule nonstrict="true|false" top="yes|no|maybe"> <!-- can be repeated -->
                <lhs>
                    <term>
                        <function> <!-- nestable -->
                            <variable name="a|..."/>
                        </function>
                    </term>
                    <variable name="a|..."/>
                </lhs>
                <rhs>$term</rhs>
            </rule>
            <conditionalrule>
                <conditions>
                    <rule/> <!-- multiple -->
                </conditions>
                <rule/>
            </conditionalrule>
        </rules>

        <signature>
            <!-- optional information which may or may not be required -->
            <!-- contextsensitive info may be added here -->
        </signature>
    </tp>
    </code>