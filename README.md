dtbooktosbsform
===============

This project provides:

1. a command line tool to transform [dtbook xml source files](http://en.wikipedia.org/wiki/DTBook)
into a braille format proprietary to [sbs](http://www.sbs.ch), and
2. a specialized `javax.xml.transform.sax.SAXTransformerFactory`
that can be used to configure applications that respect the
System property `"javax.xml.transform.TransformerFactory"`.

It uses [saxon](http://saxon.sourceforge.net/) with a [java extension](https://github.com/bwagner/LiblouisSaxonExtension)
that offers translating text into braille using [liblouis](http://code.google.com/p/liblouis/).

Usage command line tools
------------------------

    cd dtbooksbsform
    ./dtbook2sbsform.sh dtbook.xml
    
calls `saxon.sh`, transforms `dtbook.xml` and performs line breaking using `linebreak.sh` printing output onto stdout.

    ./saxon.sh
    
calls saxon, offering its rich command line interface, includes our extension function
(see `resources/xsl/dtbook2sbsform.xsl`).

    ./linebreak.sh
    
breaks lines according to sbs rules: only lines beginning with a blank will be broken. Line width is 80 chars.

Usage org.liblouis.LouisExtensionTransformerFactoryImpl
-------------------------------------------------------

    java -Djavax.xml.transform.sax.SAXTransformerFactory YourAppThatUsesJaxp

Examples can be found in the xsl tests which are performed using
[utf-x](http://utf-x.sourceforge.net/) (we're using the svn version, which has been ported to work with saxon9he).
See utfx.sh shell script. 

Prerequisite installs
------------------------

* [java](http://java.sun.com)
* [liblouis](http://code.google.com/p/liblouis/)
