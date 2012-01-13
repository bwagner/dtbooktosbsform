dtbook2sbsform
===============

This project provides:

a command line tool to transform [dtbook xml source files](http://en.wikipedia.org/wiki/DTBook)
into a braille format proprietary to [sbs](http://www.sbs.ch) using [saxon](http://saxon.sourceforge.net/) with a [java extension](https://github.com/bwagner/LiblouisSaxonExtension)
that offers translating text into braille using [liblouis](http://code.google.com/p/liblouis/).

Usage command line tools
------------------------

    cd dtbook2sbsform
    ./dtbook2sbsform.sh dtbook.xml
    
calls `saxon.sh`, transforms `dtbook.xml` and performs line breaking using `linebreak.sh` printing output onto stdout.

    ./saxon.sh
    
calls saxon, offering its rich command line interface, includes our extension function
(see `resources/xsl/dtbook2sbsform.xsl`).

    ./linebreak.sh
    
breaks lines according to sbs rules: only lines beginning with a blank will be broken. Line width is 80 chars.

    ./utfx.sh
    
Performs [utfx](http://utf-x.sourceforge.net/) (svn version) tests.

Prerequisite installs
------------------------

* [java](http://java.sun.com)
* [liblouis](http://code.google.com/p/liblouis/)

Authors
-------

**Christian Egli**

+ https://github.com/egli

**Bernhard Wagner**

+ http://xmlizer.net
+ http://github.com/bwagner

License
---------------------

Copyright 2011 SBS.

Licensed under GNU Lesser General Public License as published by the Free Software Foundation,
either [version 3](http://www.gnu.org/licenses/gpl-3.0.html) of the License, or (at your option) any later version.
