---
layout: page
title: First Document

order: 20
duration: 10
tutorial: true
instructors_notes: true
description: |
  After installation, the next thing to do is to create a new document. This will
  vary with the system being used. 

---

Creating a new document varies from system to system. If you are using OverLeaf create a 
new project and a new document called `main.tex` will be created for you. OverLeaf takes 
a project based view of LaTeX. This makes sense given most documents end up being created 
from multiple files. Other editors work work with files, and you must manage your project 
organization yourself.

To get started, in OverLeaf, create a new project. It will create an initial document for 
you with that looks like this. If you are working with a nother system, create a document
and add the information below, inserting your name, and date as you like.

```latex
\documentclass{article}   
\usepackage[utf8]{inputenc}

\title{tutorial}
\author{Your Name}
\date{April 2020}

\begin{document}

\maketitle

\section{Introduction}

\end{document}

```

The items preceded by a backslash are commands. Each command runs a macro, which are 
essentially functions. The curly braces denote input into the command, not all commands 
require input. The first command `\documentclass{article}` is required and denotes the 
broad type of document you are creating. There are others, `book`, `report`, `letter` 
and `slides` are common. The other two required commands are `\begin(document)` and 
`end{document}`.

Everything before `\begin{document` is called the *preamble*. They provide additional
information about packages to include and data for the document. The things between
`\begin{document}` and `\end{document}` are typically displayed. In this example there
is a `\maketitle` command that creates a title for the document using data from the 
*preamble* and a `\section{}` command that specifies the section name "Introduction". 


## Try It Out

* Add some text in different parts of the document. See what happeens. Do you get some errors?
* Add a section without input, what happens?










