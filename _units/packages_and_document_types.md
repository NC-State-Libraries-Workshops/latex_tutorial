---
layout: page
title: Packages and Document Classes

order: 25
duration: 10
tutorial: true
instructors_notes: true
description:
  Packages are a collection of files containing LaTeX commands and macros. They add new 
  styles, formatting and other features to your environment. Most installations
  have many installed. Here we describe how to install and use new packages.

---

Understanding packages and document classes can help you be a lot more 
efficient when writing LaTeX. Chooseing the right packages and documents well
help you set the major style and structure settings and give you the functionality
you need to get your document looking how you want it to look. 

# Packages

Packages are the primary way of adding functionality to LaTeX. Typical installations of 
LaTeX usually have thousands of packages pre-installed so you often don't have to install
any new ones. How you install packages depends on your operating system and the 
installation of LaTeX you are using. 

You may never have to install a package, but how do you know when you will need to? Typically,
you will want to add some kind of formatting or styling, you will do a web search how to do 
it, and the answer you find uses package. You try to use the package with `usepackage{}` and 
you get an error that the package isn't installed. Then  you should go 
to [CTAN](https://www.ctan.org/) find the package and install it following the instructions.


# Document Classes

Typically the first command in the preamble is `documentclass{}`. This command sets up the main
styling and structure to be used in your document, such as font and font size, margins, 
paper size, layout (portrait vs landscape) and more. The most common type used is probably 
`article`. here are some of the document classes you will see most often: 

<dl>
<dt>article</dt>	<dd>For articles in scientific journals, presentations, short reports, program documentation, invitations, ... <dd>
<dt>IEEEtran</dt>	<dd>For articles with the IEEE Transactions format.</dd>
<dt>proc</dt>	<dd>A class for proceedings based on the article class.</dd>
<dt>report</dt>	<dd>For longer reports containing several chapters, small books, thesis, ...</dd>
<dt>book</dt>	<dd>For books.</dd>
<dt>slides</dt>	<dd>For slides. The class uses big sans serif letters.</dd>
<dt>memoir</dt>	<dd>For changing sensibly the output of the document. It is based on the book class, but you can create any kind of document with it [1]</dd>
<dt>letter</dt>	<dd>For writing letters.</dd>
<dt>beamer</dt>	<dd>For writing presentations (see LaTeX/Presentations).</dd>
</dl>

This is not an exhaustive list. Anyone can make a document class, and there are 
specialized classes created by universities and publishers for instance that conform to 
their style guidelines.

You can provide options to a document class, the syntax being 
`\documentclass[option1, option2]{class_name}`. There are a fair number of options you
can use, many of which are listed here:

<dl>
<dt>10pt, 11pt, 12pt</dt>	
<dd>Sets the size of the main font in the document. If no option is specified, 10pt is assumed.</dd>
<dt>a4paper, letterpaper,...</dt>	
<dd>Defines the paper size. The default size is letterpaper; However, many European distributions
of TeX now come pre-set for A4, not Letter, and this is also true of all distributions of pdfLaTeX. 
Besides that, a5paper, b5paper, executivepaper, and legalpaper can be specified.</dd>
<dt>fleqn</dt>	
<dd>Typesets displayed formulas left-aligned instead of centered.</dd>
<dt>leqno</dt>	
<dd>Places the numbering of formulas on the left hand side instead of the right.</dd>
<dt>titlepage, notitlepage</dt>	
<dd>Specifies whether a new page should be started after the document title or not. 
The article class does not start a new page by default, while report and book do.</dd>
<dt>twocolumn</dt>	
<dd>Instructs LaTeX to typeset the document in two columns instead of one.</dd>
<dt>twoside, oneside</dt>	
<dd>Specifies whether double or single sided output should be generated. The classes 
article and report are single sided and the book class is double sided by default. 
Note that this option concerns the style of the document only. The option twoside does 
not tell the printer you use that it should actually make a two-sided printout.</dd>
<dt>landscape</dt>	<dd>Changes the layout of the document to print in landscape mode.</dd>
<dt>openright, openany</dt>	
<dd>Makes chapters begin either only on right hand pages or on the next page available. 
This does not work with the article class, as it does not know about chapters. The 
report class by default starts chapters on the next page available and the book class 
starts them on right hand pages.</dd>
<dt>draft</dt>	
<dd>makes LaTeX indicate hyphenation and justification problems with a small square in 
the right-hand margin of the problem line so they can be located quickly by a human. 
It also suppresses the inclusion of images and shows only a frame where they would 
normally occur.</dd>
</dl>


An example of using options for a document class might look like 
`\documentclass[12pt,a4paper,oneside,draft]{report}`. This would set a report
to be in 12pt type on A4 paper, but printed only on onside in draft mode.



