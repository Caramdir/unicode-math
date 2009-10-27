The UNICODE-MATH package
========================

This package will provide a complete implementation of unicode maths for
XeTeX. While I do not encourage people to use this package for production
work, I understand that it has certain uses and am making it available for
distribution. Your testing and feedback is essential to fill in the many gaps
that I miss!

Please be aware that this package is undergoing (slow) continued
development and the interface and functionality should not be considered
stable. Use at your own risk, in other words.

Unicode maths is currently supported to one degree or another by the fonts

 - [Cambria Math][0] (Microsoft, proprietry),
 - [Asana Math][1] (Apostolos Syropolous, open source),
 - [Neo Euler][2] (Khalid Hosny, open source), and
 - [STIX][3] (STI Pub, freely available when it's released).

I'm always looking for new fonts to test with, so please let me know of any
new releases.

[0]: http://www.ascenderfonts.com/font/cambria-regular.aspx
[1]: http://www.ctan.org/tex-archive/fonts/Asana-Math/
[2]: http://github.com/khaledhosny/euler-otf
[3]: http://www.aip.org/stixfonts/


PACKAGE USAGE
-------------

Please see the PDF documentation for full details. A simple beginning is:

    \usepackage{unicode-math}
    \setmathfont{Cambria Math}

Most LaTeX math should still work after this. (Let me know if it doesn't.)
Furthermore, it will be in a different font.


REQUIREMENTS
------------

As well as running XeTeX, of course, this package requires recent versions
of the expl3 and xpackages bundles.
These form the basis of the new LaTeX3 programming layer.
If you're using TeX Live 2009 or MiKTeX 2.8 then there'll be no problems.


INSTALLATION
------------

Run TeX on unicode-math.dtx to generate the package file unicode-math.sty:

    tex unicode-math.dtx

If you have the necessary fonts, you may compile the documentation
with XeLaTeX:

    xelatex unicode-math.dtx

To install the package, place unicode-math.sty and unicode-math-table.tex
in a place searched by XeLaTeX; on Mac OS X, for example:

    ~/Library/texmf/tex/xelatex/


MAINENANCE
----------

Latest developmental and archived historical versions of this package are
available from GitHub:
<http://github.com/wspr/unicode-math>

Not yet released on CTAN.

Please file bug reports with minimal examples:
<http://github.com/wspr/unicode-math/issues>

LICENCE
-------

The unicode-math package may be modified and distributed under the terms and
conditions of the [LaTeX Project Public License][LPPL], version 1.3c or
greater.

[LPPL]: http://www.latex-project.org/lppl/

This work is author-maintained and consists of the files

- unicode-math.dtx, and
- unicode-math-table.tex;

the derived files

- unicode-math.sty,
- this readme,
- unicode-math.ins;

and the test suite for this package

- testfiles/umtest-preamble.tex,
- testfiles/umtest-suite.tex,
- testfiles/umtest*.ltx,
- testfiles/umtest*.safe.png.

__________________________________
Copyright 2006-2009 Will Robertson