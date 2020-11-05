---
layout: page
title: More Formatting Text

order: 45
duration: 01
tutorial: true
instructors_notes: true
description: |
  LaTeX has very powerful tools for formatting text. Here we explore more of
  the more useful text formatting commands.

---

These text formatting tools may be a bit less used, and many require loading 
additional packages as well. None the less, we'll cover them briefly.

## Hyperlinks

Hyperlinks require the **hyperref** package. You can put it in the preamble with some options.

```latex

\usepackage[colorlinks=true,urlcolor=blue]{hyperref}

```

Then in your text you can do a few  things. If you want to link to an external website,
you can do the following.

```latex

Odio pellentesque diam volutpat \href{http://example.com}{example hyperlink} commodo.

````

A bare URL is even easier.

```latex

Odio pellentesque diam volutpat \url{http://example.com}commodo.

```


If you want to make internal links you need to both create a label, then link to that 
label. For instance if you wish to linke to the introduction section...


```latex

\section{Introduction}
\label{sec:intro}


\hyperref{sec:intro}{Linked text somewhere else.}

```

## Fonts

There are a number of ways to change the font of your document. LaTeX tends to be somewhat
opinionated in font selection, focusing on fonts with good readability. Also, how you change fonts
depends on exactly what LaTeX you install. There are also varoius packages. Most times, going with 
the default or one of the "builtin" fonts will work fine. If there is a specific font you want to 
use, you may need to research it and follow the directions for that font. In overleaf, you can often 
use the `\usepackegge{}` command in the preamble to load the desired font. 

```latex


\usepackage{times}


```

You can also change the font for an entire document doing the following.

```latex

\begin{document}

\fontfamily{phv}\selectfont      % changes font to Helvetica

All my other text.


```

You can also change the font for a section of text a similar way.


```latex

Tempus urna et pharetra pharetra. Vulputate ut pharetra sit amet aliquam id diam. 
Pellentesque habitant morbi tristique senectus et. Ut faucibus pulvinar elementum integer 
enim neque volutpat ac. Id ornare arcu odio ut sem. Sed sed risus pretium quam vulputate 
dignissim. Non diam phasellus vestibulum lorem sed risus. 


{\fontfamily{phv}\selectfont      % changes font to Helvetica
Magna fermentum iaculis eu non diam phasellus vestibulum. Eget mi proin sed libero enim 
sed faucibus. Mi in nulla posuere sollicitudin. Egestas quis ipsum suspendisse ultrices 
gravida dictum fusce ut. Interdum posuere lorem ipsum dolor sit amet consectetur 
adipiscing elit. Phasellus faucibus scelerisque eleifend donec pretium vulputate. 

Semper risus in hendrerit gravida rutrum quisque non. Elit eget gravida cum sociis natoque 
penatibus et magnis. Aliquam eleifend mi in nulla posuere sollicitudin. Eget aliquet nibh 
praesent tristique magna sit amet purus. Leo urna molestie at elementum eu facilisis 
sed odio morbi. Orci eu lobortis elementum nibh tellus molestie nunc. scetur. 
}


```

Using the curly braces like this can be a good trick for a lot of things. The curly
braces contain the commands inside to that environment defined by the braces.


## Text Color

Like fonts, changing text color should be done with care, In practice, this is 
probably more appropriate for slides and presentations. The first thing is to
use the `xcolor` package in your preamble.

```latex

\usepackage{xcolor}

```

Then much like you change fonts you can change text color, or background color.


```latex

\textcolor{blue}{my text} and my uncolored text.


{\color{pink}You can also color sections of text this way.}

```

By default you can use these colors. `black, blue, brown, cyan, darkgray, gray, green, ` 
`lightgray, lime, magenta, olive, orange, pink, purple, red, teal, violet, white, yellow.`
If you want more colors you can add more via an option for `\usepackgedvipsnames]{xcolor}`.

You can also define your own colors using the `xcolor` command `define_color` as follows.


```latex

\usepackage{xcolor}

\definecolor{new_color}{rgb}{1, 0.75, 0.25}


\begin{document}

{color{new_color}
Tempus urna et pharetra pharetra. Vulputate ut pharetra sit amet aliquam id diam. 
Pellentesque habitant morbi tristique senectus et. Ut faucibus pulvinar elementum integer 
enim neque volutpat ac. Id ornare arcu odio ut sem. Sed sed risus pretium quam vulputate 
dignissim. Non diam phasellus vestibulum lorem sed risus. }

```

This would turn the text an orange color.
