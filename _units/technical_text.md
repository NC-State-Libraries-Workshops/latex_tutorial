---
layout: page
title: Technical Text

order: 70
duration: 10
tutorial: true
instructors_notes: true
description: |
    One of the reasons LaTeX is so popular within mathematical and other communities
    are its powerful tools for formating equations and other specialized content. This
    unit reviews some of the more common tools for equations and other needs.

---


## Equations

Writing equations in LaTeX is one of the reasons it is so popular among mathmeticians 
and other fields who use a lot of equations in their writing. It is somewhat complex
so we'll just touch some of the basics. For further content, the 
[LaTeX wikibooks](https://en.wikibooks.org/wiki/LaTeX/Mathematics) page on 
equations is relatively thorough. Also, as always, a web search will usually 
give you what you need.


Each equation needs to be put in an `equation` environment. If you are developing
several lines of equations you need to put each one in its own equation environment.
Notice the equations are numbered automatically. You should also include the 
package `asmath` package in your preamble.

```latex

\begin{equation}
    x = 0
\end{equation}
\begin{equation}
    \alpha \in \Gamma
\end{equation}
\begin{equation}
    \cos (2\theta) = \cos^2 \theta - \sin^2 \theta
\end{equation}
\begin{equation}
    \frac{n!}{k!(n-k)!} = \binom {n + 1}{k}
\end{equation}
\begin{equation}
    \sqrt[n]{1+x+x^2+x^3+\dots+x^n}
\end{equation}

```


## Code and Algorithms

Writing computer code or pseudocode (algorithms) is another great use of LaTeX. Code 
and Algorithms are similar, the difference being that code is typically associated 
with a specific programming language, while algorithms (also referred to as pseudocode)
usually describe logical steps that might be implemented in any programming language.




## Algorithms

There are a number of good algorithm packages available. The LaTeX wikibook chapter on
[algorithms](https://en.wikibooks.org/wiki/LaTeX/Algorithms). Probably the best thing to 
do is to do some research and find out which ones work best for your needs and style.
For demonstration, we'll be using the `algorithm2e` package. Use that package in 
your preamble.

```latex
\begin{algorithm}[H]
 \KwData{this text}
 \KwResult{how to write algorithm with \LaTeX2e }
 initialization\;
 \While{not at end of this document}{
  read current\;
  \eIf{understand}{
   go to next section\;
   current section becomes this one\;
   }{
   go back to the beginning of current section\;
  }
 }
 \caption{How to write algorithms}
\end{algorithm}

```

## Code

To display code we use th `listings` package. There aren't as many packages it seems,
but the listings package does seem to have a lot of options, too so we'll leave it to you
to explore them visit the LaTeX wikibook 
[page](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings) on them.

There are two ways to get code to display. The first way is to enter the code into
your document as shown below.


```latex

\begin{lstlisting}

# frozen_string_literal: true

# Base decorator class for web objects.
class AbstractWebObjectDecorator < Draper::Decorator
  delegate_all

  # Define presentation-specific methods here. Helpers are accessed through
  # `helpers` (aka `h`). You can override attributes, for example:
  #
  #   def created_at
  #     helpers.content_tag :span, class: 'time' do
  #       object.created_at.strftime("%a %m/%d/%y")
  #     end
  #   end

  # rubocop:disable Metrics/AbcSize
  def slurl
    position = JSON.parse(self.position)
    href = "https://maps.secondlife.com/secondlife/#{region}/#{position['x'].round}/" \
           "#{position['y'].round}/#{position['z'].round}/"
    text = "#{region} (#{position['x'].round}, " \
           "#{position['y'].round}, #{position['z'].round})"
    h.link_to(text, href)
  end
  # rubocop:enable Metrics/AbcSize
end
\end{lstlisting}


````

The other is to load the file containg the code. 



```latex
\lstinputlisting{source_filename.py}
```

This file is rather long, and it is quite likely you only want to show a small portion.
You can specify the lines you show as follows.



```latex
\lstinputlisting[language=python, linerange={26-44,64-83}]{source_filename.py}
```

Many times, code is highlighted to increase readability. You can do this with some work. 
There is also a package called `minted`, we'll use this. We also have to use the 
`filecontents` package to get the same result.

```latex

\documentclass{article}
\usepackage[utf8]{inputenc}

\title{code}
\author{rkolendo }
\date{November 2020}
\usepackage{listings}
\usepackage{graphicx}
\usepackage{minted}
\usepackage{filecontents}

\begin{document}

\maketitle

% \inputminted[first={26-44,64-83}]{python}{pythonsample.py}
\inputminted[firstline=26, lastline=44]{python}{pythonsample.py}


\inputminted[firstline=64, lastline=83]{python}{pythonsample.py}

\end{document}


```

