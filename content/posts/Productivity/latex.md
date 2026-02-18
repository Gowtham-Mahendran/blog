---
title: "LaTeX"
description: "Minimal notes for installing and using LaTeX with VS Code"
tags: ["productivity"]
date: 2026-01-06
draft: false
---

## Installation

```bash
sudo aptitude install texlive-full
```

**Verify installation**

```bash
tex --version
```

```bash
pdflatex --version
```

`pdflatex` is the compiler used by VS Code for LaTeX builds.

## VS Codium

Install the **LaTeX Workshop** extension by **James-Yu**. See [**Visual studio code**]({{< relref "posts/development/vs-codium.md" >}}) setup.


---

Here you can find a minimal starting guide to work on latex. Some simple syntax for margins, basic text variations, headings, equations, images and tables are included.

Before starting, enable word wrapping in **VSCodium**:

**File → Preferences → Settings → Word Wrap → ON**

This makes LaTeX source files far easier to read and maintain.


**Start with a main file**

Always create a central entry point:

```tex
main.tex
```

This file defines the document layout and imports all other content.

---

**Define the document class**

Every LaTeX document starts with a class:

```tex
\documentclass{article}
```

> **LaTeX document classes**
>
> **article** → Articles in scientific journals  
> **proc** → Proceedings class  
> **report** → Reports, theses  
> **book** → Books  
> **beamer** → Slides  
> **letter** → Letters  


---

**Document boundaries**

All content must live inside:

```tex
\begin{document}

\end{document}
```

---

**Set page margins**

Use the `geometry` package for predictable layouts:

```tex
\usepackage{geometry}
\geometry{margin=1in}
```

---

**Sections and hierarchy**

```tex
\section{Title}
\subsection{Subsection}
\subsubsection{Subsubsection}
```

---

**Text formatting**

```tex
\textbf{bold}
\textit{italic}
```

---

**Code listings**

```tex
\usepackage{listings}

\begin{lstlisting}[language=Python]
print("Hello, LaTeX")
\end{lstlisting}
```

---

**Figures and images**

```tex
\usepackage{float}
\usepackage{graphicx}

\begin{figure}[H]
\centering
\includegraphics[width=0.6\textwidth]{images/plot.png}
\caption{Example}
\end{figure}
```

* `[H]` forces exact placement
* Image paths are always relative to `main.tex`

---

**Splitting content into files**

```tex
\usepackage[utf8]{inputenc}
\input{intro/intro}
```

When using secondary files like `intro.tex`, follow these rules:

1. All packages belong in `main.tex`
2. Do **not** use `\begin{document}` or `\end{document}`
3. Image paths stay relative to `main.tex`
4. Only content goes into sub-files

---

**Lists**

Bullet points

```tex
\begin{itemize}
  \item First point
  \item Second point
  \item Third point
\end{itemize}
```

numbered lists

```tex
\begin{enumerate}
  \item First
  \item Second
\end{enumerate}
```

---

**Superscripts and subscripts**

```tex
text$^{sup}$
text$_{sub}$
```

---

**Equations**

```tex
\begin{equation}
a = b + c
\end{equation}

\begin{equation}
X_L = 2\pi f L
\end{equation}
```

---

**Tables**

```tex
\begin{table}[H]
\centering
\renewcommand{\arraystretch}{1.25}
\begin{tabular}{lll}
\hline
\textbf{Parameter} & \textbf{Definition} & \textbf{Value} \\
\hline
x & y & z \\
u & v & w \\
\hline
\multicolumn{3}{c}{\textbf{Name}} \\
\hline
a & b & c \\
\hline
\end{tabular}
\caption{Caption goes here}
\end{table}
```

---

**Spacing**

To insert some space between the heading and paragraph,
```tex
\textbf{Heading:}\par\vspace{0.5em}

some paragraph text goes here....
```

`1em` corresponds to current font size and `0.5em` to half the font height.

---

**Matplotlib figures**

[Refer](https://blog.timodenk.com/exporting-matplotlib-plots-to-latex/)
