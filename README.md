# LaTeX Changes Tracker
This is a small LaTeX snippet for keeping track of changes in a manuscript. This was made as a simple replacement of the "changes" package as it does not support the \cite command.

# How to use
Copy the following snippet in the preamble of your LaTeX document.

```latex
\def\changes{1} % Set to 1 for tracking changes, set to 0 for final version

\newcommand{\deleted}[1]{\if\changes0\else\color{red}{\sout{#1}}\color{black}\fi}
\newcommand{\added}[1]{\if\changes0{#1}\else\textcolor{blue}{#1}\fi}
```
The variable "changes" can be set to 0 (= do not show changes) or 1 (= show changes)

Two commands are available:

- **\added{some text}**: If changes is 0 the argument of the command is simply printed in the pdf, otherwise it will be printed with a blue colour

- **\deleted{some text}**: If changes is 0 the argument of the command is not printed in the pdf, otherwise it will be printed with strikethrough font and red colour


