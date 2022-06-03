---
title: "A Helpful Guide on using Jupyter Notebook for Scientific Documentation - Part 3"
excerpt: "Learn about LaTex  and see the list of important LaTeX syntax."
header:
  image: /assets/images/posts/jupyter_nb_header1.jpg
  caption: "Photo by [Nick Morrison](https://unsplash.com/@nickmorrison) on [Unsplash](https://unsplash.com/)"
date: March 07, 2022
toc: true
tags:
  - Academic Writing
  - Jupyter Notebboks
  - LaTeX
  - Scientific Writing
  - Grad students
category:
  - Jupyter Notebooks
---

This is Part 3 of the series on Jupyter Notebooks for Scientific Documentation. A brief introduction of LaTeX typsetting is presented along with useful LaTeX syntax in markdown for creating scientific documents. See [Part 1](/jupyter%20notebooks/guide-jupyter-notebook-for-scientific-writing-part-1/) for introduction to Jupyter Notebook. See [Part2](/jupyter%20notebooks/guide-jupyter-notebook-for-scientific-writing-part-2/) to learn about Markdown language and useful Markdown syntaxes.
{: .notice}

## What is LaTeX?

LaTeX is a typesetting system for producing high-quality scientific documents and reports. Most people would think of LaTeX as a competition to Microsoft Word or Google Docs but technically, it is not; it is not a word processing software like MS Word or Google Docs.  

LaTeX is motivated by the idea that document authors' time must be focused on writing content instead of worrying about the appearance or the design aspect of the document. According to [The LaTeX Project](https://www.latex-project.org/about/),

> For example, consider this document:
> 
> ```
> Cartesian closed categories and the price of eggs
> Jane Doe
> September 1994
>
> Hello world!
> ```
>
> To produce this in most typesetting or word-processing systems, the author would have to decide what layout to use, so would select (say) 18pt Times Roman for the title, 12pt Times Italic for the name, and so on. This has two results: authors wasting their time with designs; and a lot of badly designed documents!
>
> LaTeX is based on the idea that it is better to leave document design to document designers, and to let authors get on with writing documents.

## Why use LaTeX?

Jupyter Notebooks understand the text written in LaTeX syntax in notebook's markdown cells using [MathJax](https://www.mathjax.org/) library. Generally, when  documents are prepared in markdown language, the LaTeX syntax is used for rendering of texts such as math equations, scientific notations, greek letters, equation numbers and alignment, etc., as these texts are not natively supported by markdown language.  

## LaTeX Syntax

### Writing Equations

Text written between dollar delimiters `$..$` will be displayed as an **inline equation** (as a part of the same paragraph). Whereas, the text written contained within double dollar delimiter `$$..$$` will be displayed as a **centered block equation** on a new line (not a part of the paragraph).  

*Example of LaTeX code for an inline equation:*  

Equation of a line is given as `$y = mx + c$`.  

*Output is rendered as:*  

Equation of a line is given as $y = mx + c$.

*Example of LaTeX code for a centered block equation:*  

Equation of a line is given by the following expression
```
$$y = mx + c$$
```

*Output is rendered as:*

Equation of a line is given by the following expression

$$y = mx + c$$

{% capture notice-text %}
* Always insert a whitespace between mathematical operators for code readability.  
* Always write centered block equation on a new line and insert blank lines before and after the centered block equation.
{% endcapture %}

<div class="notice--warning">
  <b class="no_toc"><i class="far fa-thumbs-up"></i> Best Practices.</b>
  {{ notice-text | markdownify }}
</div>

`equation*` **Environment**

The `equation*` environment allows you to create block equations and format it based on your requirements. In the `equation*` environment, you will not be writing equations between double dollar delimiter `$$..$$`. Instead, use the following LaTeX syntax.

```
\begin{equation*}
    your equation here    
\end{equation*}
```

<i class="far fa-sticky-note"></i> **Note.** There are other syntax also used for math environment, such as `\begin{math}...\end{math}` for inline math and `\begin{equation}...\end{equation}` for block equation, however I prefer the `equation*` environment as it allows manual numbering of equations.
{: .notice--info}

<i class="far fa-sticky-note"></i> **Note.** In the math mode (between dollar delimiters or in equation environment), the letters are printed in italics, as a math equation should look like. Additionally, the space characters are ignored. In certain cases, you would want to write normal text (without italics) or add whitespaces within equations. This can be done by writing the the normal text or whitespaces inside `\text{. .. ...}`. It will use the current text font, but adapt the size according to the current math style.  
{: .notice--info}

### Greek Letters

LaTeX syntax for rendering frequently used Greek letters are given below. For a detailed list of Greek letters, see [here](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols). 

**Lowercase Greek Letters**

| LaTeX code | Output | LaTeX code | Output | LaTeX code | Output | LaTeX code | Output |
| :--- | :---: | :--- | :---: | :--- | :---: | :--- | :---: |
| `$\alpha$` | $\alpha$ | `$\eta$` | $\eta$ | `$\pi$` | $\pi$ | `$\varphi$` | $\varphi$ |
| `$\beta$` | $\beta$ | `$\theta$` | $\theta$ | `$\rho$` | $\rho$ | `$\chi$` | $\chi$ |
| `$\gamma$` | $\gamma$ | `$\kappa$` | $\kappa$ | `$\varrho$` | $\varrho$ | `$\psi$` | $\psi$ |
| `$\delta$` | $\delta$ | `$\lambda$` | $\lambda$ | `$\sigma$` | $\sigma$ | `$\omega$` | $\omega$ |
| `$\epsilon$` | $\epsilon$ | `$\mu$` | $\mu$ | `$\tau$` | $\tau$ |
|`$\zeta$` | $\zeta$ | `$\xi$` | $\xi$ | `$\phi$` | $\phi$ |

**Uppercase Greek Letters**

| LaTeX code | Output | LaTeX code | Output | LaTeX code | Output |
| :--- | :---: | :--- | :---: | :--- | :---: |
| `$\Gamma$` | $\Gamma$ | `$\Lambda$` | $\Lambda$ | `$\Phi$` | $\Phi$ |
| `$\Delta$` | $\Delta$ | `$\Pi` | $\Pi$ | `$\Psi$` | $\Psi$ |
| `$\Theta$` | $\Theta$ | `$\Sigma$` | $\Sigma$ | `$\Omega$` | $\Omega$ |

### Mathematical Symbols

**Relational Operators**

| Description | LaTeX code | Output |
| :----- | :------ | :------: |
| Is proportional to | `$\propto$` | $\propto$ |
| Is equivalent to | `$\equiv$` | $\equiv$ |
| Is approximately | `$\approx$` | $\approx$ |
| Is congruent to | `$\cong$` | $\cong$ |
| Is similar or equal to | `$\simeq$` | $\simeq$ |
| Is similar to | `$\sim$` | $\sim$ |
| Is not equal to | `$\neq$` | $\neq$ |
| Is less than or equal to | `$\leq$`, `$\leqslant$` | $\leq$, $\leqslant$ |
| Is not less than | `$\nless$` | $\nless$ |
| Is neither less than nor equal to | `$\nleq$` | $\nleq$ |
| Is greater than or equal to | `$\geq$`, `$\geqslant$` | $\geq$, $\geqslant$ |
| Is not greater than | `$\ngtr$` | $\ngtr$ |
| Is neither greater than nor equal to | `$\ngeq$` | $\ngeq$ |

**Set Notation**

| Description | LaTeX code | Output |
| :----- | :------ | :------: |
| Is a proper subset of | `$\subset$` | $\subset$ |
| Is not a proper subset of | `$\not\subset$` | $\not\subset$ |
| Is a subset of | `$\subseteq$` | $\subseteq$ |
| Is not a subset of | `$\nsubseteq$` | $\nsubseteq$ |
| Is a proper superset of | `$\supset$` | $\supset$ |
| Is not a proper superset of | `$\not\supset$` | $\not\supset$ |
| Is a superset of | `$\supseteq$` | $\supseteq$ |
| Is not a superset of | `$\nsupseteq$` | $\nsupseteq$ |
| Is member of | `$\in$` | $\in$ |
| Is not member of | `$\notin$` | $\notin$ |
| Set union | `$\cup$` | $\cup$ |
| Set intersection | `$\cap$` | $\cap$ |

**Mathematical Operators**

| Description | LaTeX code | Output |
| :----- | :------ | :------: |
| Plus minus | `$\pm$` | $\pm$ |
| Minus plus | `$\mp$` | $\mp$ |
| Cross product | `$\times$` | $\times$ |
| Dot product | `$\cdot$` | $\cdot$ |
| Divided by | `$\div$` | $\div$ |
| Asterisk | `$\ast$` | $\ast$ |
| Fraction | `$\frac{\partial f}{\partial y}$` | $\frac{\partial f}{\partial x}$ |
| Summation | `$\sum$` | $\sum$ |
| Summation with limits | `$\sum\limits_{n=1}^{M}$` | $\sum\limits_{n=1}^{M}$ |
| Product | `$\prod$` | $\prod$ |
| Product with limits | `$\prod\limits_{n=1}^{M}$` | $\prod\limits_{n=1}^{M}$ |
| Integral | `$\int$` | $\int$ |
| Double integral | `$\iint$` | $\iint$ |
| Triple integral | `$\iiint$` | $\iiint$ |
| Integral with limits | `$\int\limits_{n=1}^{M}$` | $\int\limits_{n=1}^{M}$ |
| Contour integral | `$\oint$` | $\oint$ |

**Miscallaneous symbols**

| Description | LaTeX code | Output |
| :----- | :------ | :------: |
| Partial derivative | `$\partial$` | $\partial$ |
| Real part | `$\Re$` | $\Re$ |
| Imaginary part | `$\Im$` | $\Im$ |
| Nabla operator | `$\nabla$` | $\nabla$ |
| Infinity | `$\infty$` | $\infty$ |
| Three horizontal dots on the line | `$\ldots$` | $\ldots$ |
| Three horizontal dots above the line | `$\cdots$` | $\cdots$ |
| Three vertical dots | `$\vdots$` | $\vdots$ |
| Three diagonal dots | `$\ddots$` | $\ddots$ |
| Is parallel with | `$\parallel$` | $\parallel$ |
| Is perpendicular with | `$\perp$` | $\perp$ |
| Triangle | `$\triangle$` | $\triangle$ |

**Arrows and Lines**

| LaTeX code | Output | LaTeX code | Output |
| :----- | :------: | :----- | :------: |
| `$\overline{\text{A}}$` | $\overline{\text{A}}$ | `$\overrightarrow{\text{A}}$` | $\overrightarrow{\text{A}}$ |
| `$\gets$` or `$\leftarrow$`  | $\gets$ | `$\to$` or `$\rightarrow$`  | $\to$ |
| `$\Longleftarrow$` | $\Longleftarrow$ | `$\Longrightarrow$` | $\Longrightarrow$ |
| `$\Leftarrow$` | $\Leftarrow$ | `$\Rightarrow$` | $\Rightarrow$ |
| `$\longleftarrow$` | $\longleftarrow$ | `$\longrightarrow$` | $\longrightarrow$ |
| `$\Leftrightarrow$` | $\Leftrightarrow$ |`$\iff$` | $\iff$ |
| `$\leftharpoonup$` | $\leftharpoonup$ | `$\rightharpoonup$` | $\rightharpoonup$ |
| `$\leftharpoondown$` | $\leftharpoondown$ | `$\rightharpoondown$` | $\rightharpoondown$ |
| `$\rightleftharpoons$` | $\rightleftharpoons$ | `$\longleftrightarrow$` | $\longleftrightarrow$ |

### Subscripts and Superscripts

Superscripts are created by using the caret `^` delimiter and subscripts are created by using underscore `_` delimiter.

*Example LaTeX code:*

```
The quadratic equation is given as: $a{x}^{2} + bx + c = 0$  
Roots of the quadratic equation are calculated using the formula: 

$${x}_{1}, {x}_{2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$
``` 

*Output is rendered as:*

The quadratic equation is given as: $a{x}^{2} + bx + c = 0$  
Roots of the quadratic equation are calculated using the formula: 

$$x_{1}, x_{2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

<i class="far fa-thumbs-up"></i> **Best Practice.** Always write superscripted and subscripted characters within curly brackets `{}`.
{: .notice--warning}

### Numbering Equations

Single equations are numbered by writing the equation in the `equation*` environment. For manual numbering of equation, see the syntax in the below example.

*Example LaTeX code:*

```
\begin{equation*}
    a^2 + b^2 = c^2
\label{eq:1} \tag{1}
\end{equation*}
```

`\label{eq:}` is used to give the equation an identifier that you can use it for cross-referencing the equation later and `\tag{}` is used to manually number the equation.

*The output of the above LaTeX code will be rendered as*  

$$
\begin{equation*}
    a^2 + b^2 = c^2 
\label{eq:1} \tag{1}
\end{equation*}
$$

### Cross-referencing Equations

Cross-reference the above equation (1) and link to it using the following syntax: `\eqref{eq:1}`.

*Example:* The Pythagorean Theorem is given by equation $\eqref{eq:1}$. (Note that the equation number is clickable.)

### Aligning Equations in a Block

Use the `\align` environment for aligning several equations.

*Example LaTeX input:*

```
\begin{align}
    \int \sin x \text{ } dx &= - \cos x + C
    \\
    \int \sec^{2} x \text{ } dx &= \tan x + C
    \\
    \int \sec x \tan x \text{ } dx &= \sec x + C
\end{align}
```

$$
\begin{align}
    \int \sin x \text{ } dx &= - \cos x + C
    \\
    \int \sec^{2} x \text{ } dx &= \tan x + C
    \\
    \int \sec x \tan x \text{ } dx &= \sec x + C
\end{align}
$$

The equations in the block are aligned with respect to the `&` delimiter.

### Matrices

Syntax for matrix with round brackets (paranthesis)

```
$$\begin{pmatrix}
    u & v & w
    \\
    p & q & r
\end{pmatrix}$$
```

$$\begin{pmatrix}
    u & v & w
    \\
    p & q & r
\end{pmatrix}$$

The `&`  in the syntax is used as a delimiter between column elements and `\\` is used as a delimiter for new row.  

Similarly, syntax for other brakcets are as follows 

**Square brackets**

```
\begin{bmatrix} 
    u & v & w
    \\
    p & q & r
\end{bmatrix}$$
```

$$\begin{bmatrix}
    u & v & w
    \\
    p & q & r
\end{bmatrix}$$

**Curly brackets**

```
$$\begin{Bmatrix}
    u & v & w
    \\
    p & q & r
\end{Bmatrix}$$
```

$$\begin{Bmatrix}
    u & v & w
    \\
    p & q & r
\end{Bmatrix}$$

**Pipes**

```
$$\begin{vmatrix}
    u & v & w
    \\
    p & q & r
\end{vmatrix}$$
```

$$\begin{vmatrix}
    u & v & w
    \\
    p & q & r
\end{vmatrix}$$

### Brackets and Paranthesis

Use `\left` and `\right` with the brackets (round, square, and curly) to dynamically resize them in the document.

See the following example

```
$$F = G \left(\frac{m_{1} m_{2}}{r^2} \right)$$
```

It will be rendered as

$$F = G \left(\frac{m_{1} m_{2}}{r^2} \right)$$

Now, let's take a look at the rendering of equation when `\left` and `\right` are not used with the brackets.

$$F = G ( \frac{m_{1} m_{2}}{r^2} )$$


