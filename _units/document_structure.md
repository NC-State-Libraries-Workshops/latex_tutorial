---
layout: page
title: Document Structure

order: 30
duration: 15
tutorial: true
instructors_notes: true
description: |
  Much of understanding LaTeX is understanding document structure.
  Although tools like *Word* have document structure, many 
  people rely on formating rather than structure. LaTeX insists that
  you use structure or it won't format properly.

---


Word processing programs like * MS Word* have a concept of structure but it is pretty loose 
and not enforced. If you look at a *MS Word* document, you have options such as
**_Normal_**, **_Heading 1_** and **_Subtitle_**. While these have the appearance of 
structure, they are really just classes of formatting that we typically associate with 
structure. Users of *MS Word* are often inconsistent with how 
they use these, if they use them at all. This sometimes results in considerable time 
waisted when, for instance, you need to change the formatting of all the subtitles. If you 
weren't consistent, you have to reformat each one.

With **LaTeX**, the structure is strongly enforced and the formatting and styling
of your document depends on the structure. 


## Structure

As noted before, a LaTeX document is divided into two main sections, a **preamble** and 
the **document**. Everything before `\begin{document}` is the preamble. The preamble is 
where we include packages (more on that later), declare what kind of document we are 
writing, and store data and metadata about the document. The data and metadata are
often used in the document itself.

Typically everything between `\begin{document}` and `\end{document}` is displayed. 


## Environments

The `\begin{document}` used above is an example of an environment in LaTeX. Environments 
are blocks of a document with certain settings applied. They always start with the begin 
command with a setting, and a reciprocal end command. 

```latex

\begin{environment_name}
Some text
\end{environment_name}
```

Given that you always use a `begin{document}` command, you can see your top lovel environment 
is the `document` environment. You can nest other environments and commands between the begin and end. 


## Commands

LaTeX commands are more limited in scope than environments in that they typically only
apply to the place they are used. Most of the LaTeX you learn will be commands. A
command starts with a backslash, and is often followed by options in square brackets,
and arguments in curly braces. 

```latex

\commandname[option1,options2]{argument1, argument2}

```


## Sections

LaTeX forces users to structure their documents, then formats the document based on the 
structure. You've already been introduced to the `\section{}` so we'll start there. By 
default the section is numbered and requires a setion title. If you don't supply a 
section title, it will be blank which isn't usually very useful. There are also
`\subsection{}` and `subsubsection{}``. Below shows a portion of your document.

```latex

...
\section{Introduction}

\section{}
This is a blank section.

\subsection{First subsection}

\subsubsection{A sub sub section}

\subsection{Second subsection}

\section{A third section}
...


```

While sections are most commonly used, there are other levels of depth depending 
available depending on your document type. 

<table>
  <tr>
    <th>Command</th>
    <th>Level</th>
    <th>Availability</th>
  </tr>
  <tr>
    <td>\part{}</td>
    <td>-1</td>
    <td>Not in letters</td>
  </tr>
  <tr>
    <td>\chapter{}</td>
    <td>-0</td>
    <td>Only books and reports</td>
  </tr>
  <tr>
    <td>\section{}</td>
    <td>1</td>
    <td>Not in letters</td>
  </tr>
  <tr>
    <td>\subsection{}</td>
    <td>2</td>
    <td>Not in letters</td>
  </tr>
  <tr>
    <td>\subsubsection{}</td>
    <td>3</td>
    <td>Not in letters</td>
  </tr>
  <tr>
    <td>\paragraph{}</td>
    <td>4</td>
    <td>Not in letters</td>
  </tr>
  <tr>
    <td>\subparagraph{}</td>
    <td>-5</td>
    <td>Not in letters</td>
  </tr>
</table>



## Section Numbering

LaTeX automatically numbers sections in a reasonable way. However, you may need more 
control over how sections are numbered, or not numbered. You can control the depth of
numbering. By default LaTeX sets it to three. Paraghraphs are not numbered.  You can 
change this with `\setcounter{secnumdepth}{1}` which would mean  subsections are not 
numbered.

```latex

...
\title{tutorial}
\author{Robert Olendorf}
\date{April 2020}
\setcounter{secnumdepth}{1}
\begin{document}
...

```

You can also put an asterisk after any section command to turn off numbers for it.
Any sections inside the higher section will not be numbered. Following sections of 
the same level or higher will continue numbering. Notice that the unnumbered section
does not increment the count.

```latex

...
\section{A third section}

\section*{Unnumbered}
\subsection{Unnumbered Too!}
\subsubsection*{Unnumbered}


\section{A Last section is numbered}
...

```

## Other Structural Elements

### Paraghraphs

Pragraphs are text. Just type the text. Start new paragraphs by leaving a blank line between
paragraphs (return twice). We will explore more how to format paragaphs in future units.

### Abstracts

If your manuscript requires an abstract you can add it to your document. It should be placed
in the correct position, typically right after the `begin{document}`

```latex

\documentclass{article}

\begin{document}

\begin{abstract}
This is my abstract.  Brief synopsis of my article.
\end{abstract}

...

\end{document}

```

If you need a different label for your abstract you can add the following before you 
begin  your abstract.

```latex

...

\renewcommand{\abstractname}{Executive Summary}
\begin{abstract}

...

```

### Table of Contents

You can add add a table of contents with the `tableofcontents` command. Just
place it where it would naturally go in  your manuscript.

```latex

...
\begin{abstract}
    This is my abstract.
\end{abstract}

\tableofcontents
...

```

Notice that any unnumbered sectons aren't counted. You can add these by adding the 
`\addcontentsline{}{}{}` under the section you want included.

```latex

...
\section*{Unnumbered}
\addcontentsline{toc}{section}{Unnumbered}
...

```

There are also `\listoffigures` and `\listoftables` commands which will be useful when 
we learn how to insert tables and figures into your document.

## Structure in Different Document Types

The structure outlined so far pertains primarily to the **article** document type. 
Other document types may have different structural elements or not use others. 
**Books** and **Reports**, for instance have the `\chapter{}` elemenent. **Letters ** 
have very limited structural elements. The table above provides some information for 
some of the more common document types. However, you should always look at the 
documentation for your document type when in doubt.


## Try It Out

* Play with the sections, subsections and paragraphs. What happens?
* What happens with the Table of Contents as you change the sections.
* Use the `\renewcommand` to change the label of the Table of Contents.
* Research how to make presentation slides in LaTeX.
  * What is the document type?
  * Are there any special components to the preambe?
  * What structural elements are used?







