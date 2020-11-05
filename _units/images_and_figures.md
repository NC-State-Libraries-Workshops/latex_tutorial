---
layout: page
title: Figures and Tables

order: 60
duration: 20
tutorial: true
instructors_notes: true
description: |
  Inserting images and figures into text is a common need. Here we explore some of the
  ways to insert them into LaTeX documents, and some of the features associated with 
  them.

---

Adding figures and tables are a frequent need in academic writing. LaTeX calls them 
floats. LaTeX positioned them in the text based on your directives. Floats are 
also always numbered and have a catpion. While you have
considerable control over their placement and presentation it is still a bit of 
an art to get it just how you want it.

## Figures

You start a figure by declaring a figure environment. 

```latex

\begin{figure}[placement specifier]
% Figure contents
\end{figure}

```

An example would be as follows. 

```latex 


\usepackage{graphicx}
\graphicspath{ {./images/} }   

\begin{document}

% lots o'text

\begin{figure}
  \caption{An example figure}
  \centering
  \includegraphics[width=0.5\textwidth]{example_file_2.png}
\end{figure}


% more o'text

```

Technicallys speaking you don't need to wrap the graphics commands in a figure environment
, but it gives you more control so I typically include it all the tim. The `
\graphicspath{}` command allows you to collect all your figures in a single place.
This can help a lot with keeping your project organized. 

Notice the figure is not always placed exactly where you put it in the text. LaTeX tries
to find the best place for it but you may often need more control. To do this we add
placement specifiers. 


```latex

\begin{figure}[h]
  \caption{An example figure}
  \centering
  \includegraphics[width=0.5\textwidth]{example_file_2.png}
\end{figure}

```

You can change where the caption is by putting it before or after the `\includegraphics{}`
command. The `\centering` command does just as you would suspect. You can adjust the
size of the figure using the `width=` option. In this case we set the width relative to 
the widt of the text in the document. You can also specify units `width=3cm`. You can
also set the heigth, `heigth=5cm`. You can control the positioning with the following
options. You can combine them too, ie. `[ht]`

| Parameter	| Position |
| --------- | -------- |
| h	| Place the float here, i.e., approximately at the same point it occurs in the source text (however, not exactly at the spot) |
| t	| Position at the top of the page. |
| b	| Position at the bottom of the page. |
| p	| Put on a special page for floats only. |
| !	| Override internal parameters LaTeX uses for determining "good" float positions. |
| H	| Places the float at precisely the location in the LATEX code. Requires the float package, though may cause problems occasionally. This is somewhat equivalent to h!. |


These are the basics of inserting figures. For more specific needs, there are several 
packages avaialable. A quick web search will usually get you what you need.


### Wrapping Text

You can also wrap text around your figures and tables. You need to use the `wrapfig`
package and create your figure as follows.


```latex


\begin{wrapfigure}{r}{0.5\textwidth}
  \begin{center}
    \includegraphics[width=0.48\textwidth]{gull}
  \end{center}
  \caption{A gull}
\end{wrapfigure}

```

## Tables

Tables work pretty much like images, which isn't surprising since they are both 
floats. 

```latex

\begin{table}
  \centering
    \begin{tabular}{| l c r |}
    \hline
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9 \\
    \hline
    \end{tabular}
  \caption{A simple table}
\end{table}

```










