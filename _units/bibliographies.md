---
layout: page
title: Bibtex and Bibliographies

order: 80
duration: 15
tutorial: true
instructors_notes: true
description: |
    This unit explores some of LaTeX's useful bibliography tools through the 
    Bibtex file type.

---



LaTeX bibliographies are pretty powerful. They aren't quite as handy (sometimes) as 
a cite-while-you-right plugin for word, it is pretty user friendly. The first thing
we need to do is `usepackage{natbib}` in the preamble. The second is to get a 
bibliography. LaTeX usses a structured text database called BibTex. 
I am using one downloaded from https://shelah.logic.at/v1/eindex.html, 
but in practice I usually download mine using my reference manager software such as 
RefWorks, Endnote, Mendeley or Zotero. There are others too, and they all typically 
allow you export all or part of your library as as a BibTex file (.bib). I avoid
manual entry into these files because I tend to make a lot of mistakes that way. A 
full explanation of a BibTex structure is beyond this tutorial, but you can see a good
explanation [here]https://en.wikibooks.org/wiki/LaTeX/Bibliography_Management).
Below are a couple sample entries.

```bibtex

@conference{Ful83,
   author = "William Fulton",
    title = "Introduction to intersection theory in algebraic geometry",
booktitle = "Regional Conference Series in Mathematics",
   number = 54,
     year = 1983}
     
     
@article{TT81,
  author = "L\^e D{\~u}ng Trang and Bernard Teissier",
   title = "Vari\'et\'es polaires locales et classes de {C}hern des
            vari\'et\'es singuli\`eres",
 journal = "Ann. of Math.",
  volume = 114,
    year = 1981,
   pages = "457--491"}   


```

There are three parts to a BibTex record. First declares the type of resource, there
are a number such as @conference, @article, @book, @thesis. The next part, just inside
the opening curly brace is the record ID. The rest is metadata. Different record 
types use different metadta, but it is usually self explanatory.


Download the sample database from ttps://shelah.logic.at/v1/eindex.html and put it in your
project folder. Now you can start citing from your BibTex database in your text

```latex

\documentclass{article}
\usepackage[utf8]{inputenc}

\title{bibtemp}
\author{rkolendo}
\date{November 2020}

\usepackage{natbib}
\usepackage{graphicx}

\begin{document}

\maketitle

\section{Introduction}
There is a theory which states that if ever anyone discovers exactly what the Universe is for and why it is here, it will instantly disappear and be replaced by something even more bizarre and inexplicable.
There is another theory which states that this has already happened \citet{MP81}.

\begin{figure}[h!]
\centering
\includegraphics[scale=1.7]{universe}
\caption{The Universe}
\label{fig:universe}
\end{figure}

\section{Conclusion}
``I always thought something was fundamentally wrong with the universe'' \citep{Ful83}

\bibliographystyle{apalike}
\bibliography{database}
\end{document}

```