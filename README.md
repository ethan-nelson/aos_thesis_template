AOS Thesis Template
===================

[![Build Status](https://travis-ci.org/ethan-nelson/aos_thesis_template.svg?branch=master)](https://travis-ci.org/ethan-nelson/aos_thesis_template)

This repository contains an unofficial Department of Atmospheric and Oceanic Sciences template for theses in LaTeX. Both the base LaTeX and extra installations are required as this template relies on many packages. Additionally, students have had success using the template out of the box on [ShareLaTeX](https://www.sharelatex.com) (thanks Marian!).

The directory structure is as follows (sorted by importance):

```
aos_thesis_template
|   Thesis.tex         the main file to run LaTeX on
|   Thesis.cls         contains global variables like your name
|   Bibilography.bib   bibtex file containing references
|   Thesis.pdf         a sample compiled file (or eventually your thesis)
|   README.md          what you are reading
|   ametsoc.bst        American Meteorological Society bibliography styling
|   .gitignore         extensions that are ignored if using git
|   .travis.yml        configuration file for Travis-CI
|
∟--Chapter/
|   |   Chapter1.tex           a sample chapter file example
|   |   ChapterTemplate.tex    a chapter template to copy
|
∟--Appendice/
|   |   AppendixA.tex          a sample appendix file example
|   |   AppendixTemplate.tex   an appendix template to copy
|
∟--Figure/
|   |   atrain.jpeg            a sample figure file
|
```


How to Compile
--------------

The easiest way to completely compile the document from scratch is to run this command sequence from the `aos_thesis_template` folder:

```
pdflatex Thesis
bibtex Thesis
pdflatex Thesis
pdflatex Thesis
```

If you're curious about why you have to run `pdflatex` so many times, check out [this TeX StackExchange answer](https://tex.stackexchange.com/a/53236/74626).

Alternatively, if you use a TeX program such as TeXShop, open `Thesis.tex` and run the aforementioned commands on that file.

Customizations
--------------

* `Thesis.cls`: First, basic information must be added to this file. Such information includes the author name, committee members and their roles, and the graduation month and year. Additional customization of the thesis like the page margins or signature page is possible as well, but not recommended.

* `Thesis.tex`: The front matter of the thesis (information between the signature page and the table of contents) is written in this file. Though all of the pages are defined, they may be unnecessary for your thesis (e.g. physical constants). If that is the case, you may comment out everything in that block.
Beyond the front matter, this file is also where you must specify the chapter and appendix files to compile into your thesis. If you have less than 10 chapters and 10 appendices, no further modifications to this file are necessary.
Finally, if you want to change the formatting of the bibliography, alter the `\bibliographystyle` command near the end of the file.

* `Chapters/ChapterN.tex`: These files are where you will place most of your thesis constant! Information about the chapter--title, short title, and number--are specified at the top of each chapter file. To add another chapter, you can copy either the `Chapter1.tex` or `ChapterTemplate.tex` files. Treat matter in these files like a regular LaTeX file: `\figure`, `\itemize`, and other commands can be used as normal. See below for further information about commands you can use to write out a hyperlinked "Chapter X".

* `Appendices/AppendixX.tex`: These files are for appended material that should be separated from the main text. Appendices appear after the chapter text but before the bibliography. To add another appendix, you can copy either the `AppendixA.tex` or `AppendixTemplate.tex` files. Again, these files act just like regular LaTeX files. If you do not want any appendices to show up, simply delete the supplied `AppendixA.tex` file and that section will be ignored during compilation (you can retaim the template file).


Variables
---------

* `\thesistitle{}`: The title of your thesis.
* `\degree{}`: The degree level (e.g. Master of Science).
* `\subject{}`: Department (Atmospheric and Oceanic Sciences).
* `\authors{}`: Your name (plural to differentiate from LaTeX's author comamnd).
* `\committeenameone{}`: The first committee member or reader name (usually your advisor).
* `\committeeroleone{}`: The role of the first member (usually Committee Chair or Faculty Advisor).
* `\committeenametwo{}`: The second committee member or reader name.
* `\committeeroletwo{}`: The role of the second member (usually Faculty Member).
* `\committeenamethree{}`: The third committee member or reader name.
* `\committeerolethree{}`: The role of the third member (usually Faculty Member).
* `\university{}`: The name of the university (University of Wisconsin--Madison).
* `\graduationmonth{}`: The month of the official graduation in the semester you are finishing (May, August, or December).
* `\graduationyear{}`: The year of the official graduation.

Commands
--------

* `\fref{fig:N}`: Adds text "Figure N" and creates a clickable reference to that figure. The figure must have `\label{fig:N}`.
* `\tref{tab:N}`: Adds text "Table N" and creates a clickable reference to that table. The table must have `\label{tab:N}`.
* `\eref{eqn:N}`: Adds text "Equation N" and creates a clickable reference to that equation. The equation must have `\label{eqn:N}`.
* `\cref{chp:N}`: Adds text "Chapter N" and creates a clickable reference to that chapter. The chapter must have `\label{chp:N}`.
* `\sref{sec:N}`: Adds text "Section N" and creates a clickable reference to that section. The section must have `\label{sec:N}`.
* `\ssref{ssec:N}`: Adds text "Subsection N" and creates a clickable reference to that subsection. The subsection must have `\label{ssec:N}`.
* `\aref{app:N}`: Adds text "Appendix N" and creates a clickable reference to that appendix. The appendix must have `\label{app:N}`.


