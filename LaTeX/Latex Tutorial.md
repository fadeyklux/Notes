Latex Tutorial
================
<font color = green> a note based on LaTeX-Tutorial.com</font>

01 First Document
-----------------
-----------------------
###The basic layout of a LaTex file
```latex
    \documentclass{article}
    \begin{document}
        Hello World!
    \end{document}
```
+ All commands share the following structure:
    \commandname{option}
+ An environment is simply an area of your document where certain typesetting rules apply.
+ it is imperative the document environment is the topmost environment
```latex
    % Valid:
    \begin{document}
        \begin{environment1}
            \begin{environment2}
            \end{environment2}
        \end{environment1}
    \end{document}
    
    % Also invalid:
    \begin{environment}
        \begin{document}
        \end{document}
    \end{environment}
```
###Adding a title page
```latex
\documentclass{article}

\title{My first document}
\date{2013-09-01}
\author{John Doe}

\begin{document}
  \pagenumbering{gobble}
  \maketitle
  \newpage
  \pagenumbering{arabic}

  Hello World!
\end{document}
```
### Summary
+ A document has a preamble and document part
+ The document environment must be defined
+ Commands beginning with a backslash \, environments have a begin and end tag
+ Useful settings for pagenumbering:
    + gobble - no numbers
    + arabic - arabic numbers
    + roman - roman numbers
