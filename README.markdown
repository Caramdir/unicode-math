The UNICODE-MATH package
========================

This package will provide a complete implementation of unicode maths for
XeTeX. While I do not encourage people to use this package for production
work, I understand that it has certain uses and am making it available for
distribution. Your testing and feedback is essential to fill in the many gaps
that I miss!

The package will soon also work under LuaTeX, but this is not yet supported.

Please be aware that this package is undergoing continued development and the
interface and functionality should not be considered completely stable. But
the more the package is used the more stable it will become. (Things are generally working now; it is only minutiae that may change in the future.)

Unicode maths is currently supported to one degree or another by the fonts

 - [Cambria Math][CM] (Microsoft),
 - [Asana Math][AM] (Apostolos Syropolous),
 - [Neo Euler][NE] (Khaled Hosny),
 - [STIX][SM] (STI Pub), and
 - [XITS Math][XM] (Khaled Hosny).

With the exception of Cambria Math, which is proprietry, the fonts above
are all freely available and released under the [Open Font Licence][OFL].

I'm always looking for new fonts to test with, so please let me know of any
new releases.

[CM]: http://www.ascenderfonts.com/font/cambria-regular.aspx
[AM]: http://www.ctan.org/tex-archive/fonts/Asana-Math/
[NE]: http://github.com/khaledhosny/euler-otf
[SM]: http://www.aip.org/stixfonts/
[XM]: http://github.com/khaledhosny/xits-math
[OFL]: http://scripts.sil.org/OFL

PACKAGE USAGE
-------------

Please see the PDF documentation for full details. A simple beginning is:

    \usepackage{unicode-math}
    \setmathfont{Cambria Math}

Most LaTeX math should still work after this. (Let me know if it doesn't.)
Furthermore, it will be in a different font.


REQUIREMENTS
------------

As well as running XeTeX or LuaTeX this package requires recent versions
of the fontspec, expl3 and xpackages packages. If you're using TeX Live 2010
then there'll be no problems.


MAINTENANCE
-----------

The current release version is available from CTAN:
> <http://tug.ctan.org/pkg/unicode-math>

Latest developmental and archived historical versions are
available from Github:
> <http://github.com/wspr/unicode-math>

Please file bug reports with minimal examples:
> <http://github.com/wspr/unicode-math/issues>


INSTALLATION
------------

The steps below assume that you have obtained unicode-math either from CTAN or
Github and you wish to install the package yourself. If you are using TeX Live
2010 or later, you may install the latest release version of the package with

    sudo tlmgr update unicode-math

Installation and compilation are automated by the Makefile; see below for the
manual procedure. To re-compile the documentation (requiring XeLaTeX and a
variety of installed fonts):

    make doc

To install unicode-math in your home texmf tree:

    make install

To install it for all users in your system-wide local texmf tree:

    make install-sys

See `make help` for further information.


### Manual procedure

Run TeX on unicode-math.dtx to generate the package file unicode-math.sty:

    tex unicode-math.dtx

If you have the necessary fonts, you may compile the documentation
with XeLaTeX:

    xelatex unicode-math.dtx

To install the package, place unicode-math.sty and unicode-math-table.tex in a
location searched by XeLaTeX, inside the directory structure
`<texmf>/tex/latex/unicode-math/`. The appropriate `<texmf>` location for a
single-user installation can be found with

    kpsewhich --var-value TEXMFHOME

For a system-wide (multi-user) installation, use the location returned by

    kpsewhich --var-value TEXMFLOCAL


TEST SUITE
----------

After installation you can initialise the testsuite with

    make initest

Subsequently, the test suite may be executed with

    make test

Both of these operations will take quite some time and require ImageMagick's
`convert` tool to be installed. They are only necessary if you wish to make
changes to unicode-math yourself (be sure to initialise the test suite
*before* any changes are made to the package) and you wish to ensure that your
changes have not affected the standard behaviour.


CHANGE HISTORY
--------------

- v0.5b (2010/09/19): Tune-up

  * Added missing symbols/synonyms:  
      \diamond  \smallint  \emptyset  \hbar  \backepsilon  \eth
  * \overline works for LuaLaTeX
  * Fix \slash; previously, it overwrote the text definition
  * \vartriangle now has the correct math class

- v0.5a (2010/07/14): TeX Live 2010 release

  * Numerous documentation improvements
  * Bug fix against stray catcode changes
  * Add `\mathcal` and `\mathbfcal` as distinct from the Script style; these are only supported by the XITS fonts at present
  * Small changes to the range of symbols offered (especially note that `\ac` is now `\invlazys` to avoid acronym package clash)
  * Superscripts are allowed after primes (as they should be)
  * Numerous LuaLaTeX improvements, including roots and over/under braces.

- v0.5 (2010/06/03): Initial CTAN release


LICENCE
-------

The unicode-math package may be modified and distributed under the terms and
conditions of the [LaTeX Project Public License][LPPL], version 1.3c or
greater.

[LPPL]: http://www.latex-project.org/lppl/

This work is author-maintained and consists of the files

- unicode-math.dtx,
- unicode-math-table.tex,
- unimath-example.ltx,
- unimath-symbols.ltx;

the derived file

- unicode-math.sty;

the compiled documentation files

- unicode-math.pdf,
- unicode-math-testsuite.pdf,
- unimath-example.pdf,
- unimath-symbols.pdf;

and the test suite for this package

- testfiles/umtest-preamble.tex,
- testfiles/umtest-suite.tex,
- testfiles/umtest*.ltx,
- testfiles/umtest*.safe.png.

__________________________________
Copyright 2006-2010 Will Robertson
