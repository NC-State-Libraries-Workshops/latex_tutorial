---
layout: page
title: Formatting Text

order: 40
duration: 15
tutorial: true
instructors_notes: true
description: |
  LaTeX has very powerful tools for formatting text. Here we explore some of
  the more useful text formatting commands.

---

LaTeX gives you great control over how your text is formatted. There is far more 
than we can cover here, so we'll just introduce some common formatting techniques and
commands. Of course if you need a specific kind of formatting, your only a quick
web search away from the answer.

## Spacing

Controlling line spacing (the whitespace between lines of text) is one of the more common 
tasks when creating a document. In LaTeX, you can set the global spacing using the 
`\linespread{factor}` in your preamble. A value of 1 is normal, 1.3 is 1 and a "one and 
a half" spacing and 1.6 is "double" spaced. It doesn't affect the font size (how big 
the characters are) or the space between words (kearning).

`\linespread{}` can only be applied over an entire document. To have more find grained 
control over line spacing, for instance double spaced text and single spaced footnotes,
you can use the `setspace` package. 

```latex

\documentclass{article}
% ...   other includes
\usepackage{setspace}

% ...  other front matter
\doublespacing   % set global double spacing

% ...
% ...

begin{document}

Some text

\begin{singlespace}   % start single spaced text

Donec bibendum, lacus ultrices aliquam sollicitudin, ex risus molestie nunc, dignissim 
gravida orci turpis in libero. Maecenas ex nisl, consectetur et blandit vitae, fermentum 
eget sapien. Ut commodo eros libero, eu tristique sem consectetur a. 

\end{singlespace}

% ...

\begin{spacing}{2.5}   % specifying your own spacing

Vivamus maximus mi eget massa finibus, sed mattis arcu venenatis. Nulla eget sem ac erat 
sagittis consectetur at ac mi. Nunc sit amet sagittis elit. Proin sit amet efficitur 
mauris. Etiam sodales, orci pretium suscipit bibendum, leo leo mollis purus, tristique 
laoreet enim ex sit amet augue. 

\end{spacing}



end{document}

```

LaTeX considers manually spacing individual words, sentences and paragrapsh as against 
its philosophy. That being said there are probably packages that will do it, but it
will usually lead to poor formatting.

## Non Breaking Whitespace

Often you need a space, but don't want a line break between the two tokens. For instance
a name, a number and units and others. LaTeX uses a tilde `~` for this.

```latex

R.~Citezen
EUR~50
```

## Hyphenation

Often words are hyphenated at the end of lines. Latex handles this automatically. If
you find that some words are being hyphenated that you do not want hyphenated you
can add `\hyphenation{word list}` into your preamble. You can also specify where words
get hyphenated. For example,  ``\hyphenation{fortran Hy-phen-a-tion},` would prevent 
LaTeX from being hyphenated at all, and the words hyphenation can be hyphenated at any 
of the specified positions.

## Quotes

Quotes are actually a bit complicated. In practice, most people using word processing 
programs quote incorrectly. LaTeX tends to enforce correct quoting. Opening single 
quotes are creating using a grave accent **`**, located to the left of the number one
on most keyboards. The closing quote is accomplished with an apostrophe **'**, found
to the right of the semicolon **;** on most keyboards. Double quotes just repeat the 
character. More specialized quotes are also available as shown below.

```latex

a single `quote' in LaTeX
a double ``quote'' in LaTeX
first ,,quote'' is on the baseline
german ,,quotation`` marks
french <<quotation>> marks
``nested `quotation' marks ''

```

## Special Characters and formatting

LaTeX supports special characters a variety of ways. You can use UTF8 encoding, and 
there are also a number of special escape codes to generate special characters. 
Read this [documentation](https://en.wikibooks.org/wiki/LaTeX/Special_Characters)
for more information.

Below is a list of some of the more common situations that might arise.

```latex


Normal Text\textsubscript{subscript}  % subscript
Normal 3\textsuperscript{rd}   % superscript

\textgreater  % greater than
\textless     % less than

\textbackslash

\copyright   % copyright
\textcircled{t} % the text in a circle

```




## Dashes and Hyphens


There are four types of dashes in LaTeX, : ‘-’(-) hyphen , ‘--’(–) en-dash , ‘---’(—) 
em-dash and ‘{\displaystyle -}-’(−) minus sign. They have different purposes:

```latex

-         % inter-word
--        % range i.e. 1--10
---       % puncuatio dash
$-$       % minus sign


```

There is so much more to this topic. It is impossible to cover entirely in a tutorial. 
The best advice is to perform a web search for what you want to do. In time you will
memorize the most often used commands.


## Superscript and Subscript

Supersciprt and subscript are pretty easy in LaTeX.

```latex

Super\textsuperscript{script}

Sub\textsubscript{script}


```




