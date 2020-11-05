---
layout: page
title: Formatting Paragraphs

order: 50
duration: 15
tutorial: true
instructors_notes: true
description: |
  The default paragraph settings for LaTeX are usually appropriate for academic writing.
  However, should you need to change them for a document or specific paragraphs, this 
  unit will describe how.

---


The default paragraph settings for LaTeX are usually appropriate for academic writing.
There are, none the less, many ways to adjust the formatting of paragraphs to suit 
your needs.

## Paragraph Alignment

By default, LaTeX justifies both margins. This is usually the best option for most 
academic writing. Should you need to change this however, its relatively easy. 
There are three ways to justify paragraphs and three commands to do it.

| Alignment | Environment | Command |
| --- | --- | --- | 
| Left justified | flushleft | \raggedright |
| Right justified | flushright | \raggedleft |
| Center | center | \centering |

Using the environment to set the alignment is done as follows using the `\begin` and 
`\end` commands.


```latex

Some text here.

\begin{flushright}
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt 
ut labore et dolore magna aliqua. Quis commodo odio aenean sed adipiscing diam. Sit amet 
consectetur adipiscing elit duis tristique. Eros in cursus turpis massa tincidunt. Nam
libero justo laoreet sit amet cursus sit amet. Sollicitudin ac orci phasellus egestas tellus 
rutrum tellus pellentesque eu. Sit amet commodo nulla facilisi nullam vehicula ipsum a 
arcu. Sagittis purus sit amet volutpat consequat mauris nunc congue. Ut diam quam nulla 
porttitor. Vitae proin sagittis nisl rhoncus mattis rhoncus urna neque viverra. Ornare 
arcu dui vivamus arcu felis bibendum. Porttitor lacus luctus accumsan tortor posuere ac. 
Nibh praesent tristique magna sit amet purus gravida quis. Nec tincidunt praesent 
semper feugiat nibh sed pulvinar proin.
\end{flushright}

Some more text here.

```

Everything between begin and end will be flush on the right side and ragged on the left.
If you use the commands, such as `\raggedright` everything after the command will be
aligned that way until you issue another command. To get it back to the default settings
you need to use the `ragged2e` package

```latex

\usepackage{ragged2e}

...

\begin{document}

Some text here.

\raggedright Odio pellentesque diam volutpat commodo. Ac odio tempor orci dapibus 
ultrices in. Est ultricies integer quis auctor elit. Ullamcorper sit amet risus nullam.
Urna et pharetra pharetra massa massa ultricies. Eu volutpat odio facilisis mauris. 
Rutrum tellus pellentesque eu tincidunt tortor aliquam. Fames ac turpis egestas sed tempus
urna et. Tellus mauris a diam maecenas. Nibh cras pulvinar mattis nunc sed blandit
libero volutpat sed. Ultricies lacus sed turpis tincidunt id aliquet.

\justify  % resets alignment to the default value.

More default justified text.

```

Which ever method you use is up to you. Using environments may be easier for smaller 
blocks of text and commands might be easier for large blocks, but either way works.


## Paragraph Indent

By default the first paragraph after a heading is not indented. Following paragraphs are indented
by the default value of 15pts. You can change this with the `\setlength` command in the preamble. 
You could also put it in the body of your document, which would adjust the indent from that point on
until its changed again.

```latex

\setlength{\parindent}{1cm}

```

To indent and unindented paragraph use `\indent` and conversley use `\noindent` to 
remove the indent from and otherwise indented paragraph.

If you set indent to zero, it becomes difficult to tell when paragraphs begin and end.
You can use the `parskip` package. 

```latex

\usepackage{parskip}
\setlength{\parindent}{0pt} 
\setlength{\parskip}{1cm}

```


