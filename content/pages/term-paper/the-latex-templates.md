---
content_type: page
description: This section provides LaTeX templates.
learning_resource_types: []
ocw_type: CourseSection
parent_title: Term Paper
parent_type: CourseSection
parent_uid: 7a9328d4-e766-d2bf-34c8-47b147aad85e
title: The LaTeX Templates
uid: 4d54df96-68ab-f323-d57a-26d3e81b5eac
---

LaTeX (and its ancestor TeX) are widely used in academic and technical publishing. They are “mark-up” languages, like HTML, that tell a processor how to construct mathematical expressions that look like typeset text. One of the objectives of this assignment is to give you an experience preparing a physics paper for “publication.” When practicing physicists submit papers to the _Physical Review_, they do so by emailing a LaTeX file, and perhaps some postscript figures, to the editorial office. Since your paper will be published in the _8.06_ _Physical Review_, you will do essentially the same, except our “publisher” prefers to your submitted paper to be in final pdf format.

Although many 8.06 students have had previous exposure to LaTeX, some have not. To facilitate writing and publication of your finished papers, we have put {{% resource_link ed4bf42f-ee07-ef1e-1a82-3148a3d745f9 "a template for an article in the ReVTeX format (PDF)" %}} used by _Physical Review_ for you to download. If ReVTeX is not installed on your machine, you can download it from [ReVTeX page](https://journals.aps.org/revtex).

To get started, you need only download the templates, open them in your favorite editor (such as emacs), and notice the way the LaTeX template deals with title pages, footnotes, references, equations, mathematical symbols in text and set off from text, equation labels, tabs, and so forth. You can construct your paper by cutting the text out of the template text and inserting your own.

You should begin by downloading the template and making sure that you can LaTeX it successfully to produce output that looks like the hard copy of the template paper posted on the course web page.

In order to do this in unix, you will need the commands:

*   `pdflatex filename.tex` or `pdflatex filename` will run the LaTeX typesetting program to produce typeset output from your input file. If there are errors in your LaTeX file, the file `filename.log` will contain error messages that are usually helpful. (Note that you will need to run LaTeX twice on the file, in order for all the references to bibliographic items and equation numbers to come out right.)
*   `bibtex filename` will optionally process a separate `bib` file if you choose to use this for your bibliography. If you do this, you will need to run `pdflatex` once before running `bibtex` and twice afterwards.
*   `latexmk` \--pdf filename will run `pdflatex` and `bibtex` as many times as necessary to update the `pdf` file. Why not always use this program? When there are compiling errors, it can be more annoying to use.
*   `latex filename.tex` and `dvips filename.dvi -o` will create first a `dvi` file and then a `ps` file. `ps2pdf filename.ps` can then optionally create a `pdf` file. This more old-fashioned approach may be preferable when printing on Athena—MIT's academic computing environment, but usually you will want to go straight to pdf using `pdflatex`.

Figures can be included in `jpg`, `png`, `pdf` or `eps` formats. If `includegraphics` is used without an extension, latex/pdflatex will search for a valid extension. The one catch is that `eps` formats are not automatically supported by `pdflatex`. However, the template provided uses the package `epstopdf` so that when includegraphics encounters an eps file it will automatically convert it to pdf. If you know how to produce illustrations in one of these formats, the template will illustrate how to incorporate them into your paper. Most graphics packages can generate eps or pdf output.

The advantage of these formats over the more common jpg or png formats is that vector graphics resize more gracefully than bitmaps.

We strongly urge people who are new at LaTeX to communicate with classmates. Likewise we strongly encourage LaTeX wizards to help the less experienced with the nuances of the language.

For Mac OS X users, the program TeXShop (available as part of the [MacTex package](https://www.tug.org/mactex/)) can be a good alternative to the command line. TeXShop combines a text editor with a TeX compiler, and has the feature that Cmd-clicking on one window will jump to the corresponding point in the other window. For Windows users, LaTeX can be downloaded from the [MiKTeX project page](https://miktex.org/) and this includes a program TeXworks (also available on other platforms) with similar features to TexShop. On any platform, emacs has extensive LaTeX support, including a semi-WYSIWYG ability to preview equations within the editor.