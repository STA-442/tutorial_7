
<!-- README.md is generated from README.Rmd. Please edit that file -->

# tutorial_7

This tutorial features two markdown files (and their knitted versions):

-   rmarkdown-mathmode.Rmd - This document gives a short tutorial on
    writing equations/statistical models within Rmarkdown. This will
    likely be useful for assignments and any future work you do.
-   glmer-tutorial - We walk through doing a multilevel logistic
    regression to analyse how referees call fouls in college basketball.

The rmarkdown-mathmode file is reproduced here in the readme for your
reference.

## Introduction

I have asked that all of your assignments be submitted via R markdown
which is ideal for presenting the results from data analysis. Rmarkdown
can be used as a general scientific writing tool as well, meaning, you
can easily write out all kinds of formula’s and equations. In this very
short tutorial I will show you how use “math mode” within Rmarkdown and
point you to some other tutorial resources.

## Math Mode

Entering math mode in Rmarkdown is as simple as using a dollar sign
symbol (`$`). Anything placed in between a starting `$` symbol and
closing `$` symbol will be interpreted via Rmarkdown’s math interpreter.
Remember to not leave any spaces between your opening and closing `$`
symbols. For example

    $ x + y $

is not valid while this expression

    $x + y$

is valid. In this expression: `$x + y`, Rmarkdown will enter math mode
and display this equation will all that stylings LateX users are
accustomed to. The expression wil render as *x* + *y*.

Using a single set of dollar signs to enclose an equation is used for
inline styling. That is when you want to have an equation written as
part of a paragraph, like this one here *y* = *α* + *β* × *x* (which was
written as `$y = \alpha + \beta\times x$`).

If you want to write a displayed equation, which renders on it’s own
line (and centered), you use 2 dollar signs on either side of your text.
For example, using our example from the previous paragraph,
`$$y = \alpha + \beta\times x$$` will render as
*y* = *α* + *β* × *x*

This is helpful when we have more complicated equations that need be
positioned prominently or need a little more space to be displayed
properly.

## Commonly used mathematical expressions

Here I will cover a few commonly used notations.

#### Greek Letters

We often use Greek letters when describing a statistical model. These
can be rendered by using a backslash `\` followed by the spelling of the
greek letter you want. You can capitalize the spelling to get the
uppercase version. For example:

-   `$\alpha$` - is *α*
-   `$\beta$` - is *β*
-   `$\delta$` - is *δ*
-   `$\gamma$` - is *γ*
-   `$\sigma$` - is *σ*
-   `$\Sigma$` - is *Σ*

and so on.

#### Fractions

Writing fractions is also pretty straight forward. We just use
`$\frac{}{}` Where whatever we put in between the first set of brackets
ends up in the numerator while the stuff we put in the second bracket
goes to the denominator.

For example

    $$\frac{(a + b)^2}{b^2}$$

will render as:

$$\\frac{(a + b)^2}{b^2}$$

You may often have fractions within fractions:

    $$\frac{(a + b)^2}{\frac{1}{2}a + \frac{1}{2}}$$

$$\\frac{(a + b)^2}{\\Big(\\frac{1}{2}a + \\frac{1}{2}b\\Big)}$$

Note the use of `\Big(` and `\Big)` for the parentheses. This tells math
mode to make these parentheses larger to fit the equation we are making.

#### Sub Scripts and Super Scripts

You may have noticed the use of `$b^2$` to make a superscript 2. We can
`_` and `^` to create sub and superscripts. Let’s try this out

    $$a^2 + a^4 + a^8 + a^16$$

*a*<sup>2</sup> + *a*<sup>4</sup> + *a*<sup>8</sup> + *a*<sup>16</sup>

hmmm, the last `$a^16$` didn’t render properly. This is between the sub
and superscript notation only looks at the first value. If you wish to
make more than one value appear in a sub or super script you can wrap
the values in braces `{}`

    $$a^2 + a^4 + a^8 + a^{16}$$

*a*<sup>2</sup> + *a*<sup>4</sup> + *a*<sup>8</sup> + *a*<sup>16</sup>

#### Regular Text

Sometimes you want to write some regualar words that don’t have any
styling applied to them in an equation. We can applish this with the use
of the keyword. See the following example

    $$\text{My Equation} = \alpha + \beta\text{my_variable}$$

My Equation = *α* + *β* × my_variable

#### Summations

Summations are very common, and also very easy making use of the `\sum`
keyword and the sub/superscript notation we just learned.

    $$\text{mean value} = \frac{\sum_{i=1}^{n} x_i}{n}$$

$$\\text{mean value} = \\sum\_{i=1}^{n}\\frac{x_i}{n}$$

#### Common Math Notation

Here are some commonly used math notations

-   Less than: `$x \lt y$` - is *x* \< *y*
-   Greater than: `$x \gt y$` - is *x* \> *y*
-   Greater than or equal to `$x \ge y$` - is *x* ≥ *y*
-   Less than or equal to `$x \le y$` - is *x* ≤ *y*
-   Not equal to`$x \ne y$` - is *x* ≠ *y*
-   Approximately equal to `$x \approx y$` - is *x* ≈ *y*
-   Is proportional to `$x \propto y$` - is *x* ∝ *y*
-   Is distributed as (squiggly line) `$y \sim N(0, 1)$` - is
    *y* ∼ *N*(0,1)
-   A hat for an estimate `$\hat{y}$` - is *ŷ*
-   A bar for an estimate `$\bar{y}$` - is *ȳ*
-   N choose k `${n \choose k}$` - ${n \\choose k}$
-   More general use binom: `$\binom{n}{k}$` - $\\binom{n}{k}$
    -   for example `$\binom{n+1}{x + y + z}$` -
        $\\binom{n+1}{x + y + z}$

#### Exercise 1.

Write out the probability mass function for the binomial distribution
shown below. Try doing on your own. If you get stuck, you can see the
solution by looking at the source code for this file. You can make the
three dots between 2 and n as `$\dots$` which renders as: …

$$P(x; p, n) = \\binom{n}{x}(p)^x(1-p)^{(n-x)}, \\text{ for } x = 0, 1,2, \\ldots, n$$

#### Arrays and Matrices

You can create arrays of numbers the `\begin{array}` and `\end{array}`
keywords. For start an array with `\begin{array}` and we end an array
with `\end{array}`. Within an array we add new columns with `&` and we
add new rows with `\\`. Beside the begin array keyword we tell Rmarkdown
the positioning of each column (c for center, l for left and r for
right. For example, the following array has 3 rows, and 3 columns. Each
entry is centered (`{ccc}`)

    $$\begin{array}{ccc}
    x_{11} & x_{12} & x_{13}\\
    x_{21} & x_{22} & x_{23} \\
    x_{31} & x_{32} & x_{33} \\
    \end{array}$$

This will render as

$$
$$

Instead of an array we can create a matrix with square brackets using
`\begin{bmatrix}` as:

    $$X = \begin{bmatrix}
    1 & x_{1}\\
    1 & x_{2}\\
    1 & x_{3}
    \end{bmatrix}$$

$$X = \\begin{bmatrix}
1 & x\_{1}\\\\
1 & x\_{2}\\\\
1 & x\_{3}
\\end{bmatrix}$$

We can create a matrix with parentheses with `\begin{pmatrix}`, as in

    $$X = \begin{pmatrix}
    1 & x_{1}\\
    1 & x_{2}\\
    1 & x_{3}
    \end{pmatrix}$$

$$X = \\begin{pmatrix}
1 & x\_{1}\\\\
1 & x\_{2}\\\\
1 & x\_{3}
\\end{pmatrix}$$

We can create a system of equations with the `\being{aligned}` keyword.
Here we put an `&` symbol in the spot we wish to align. For example

    $$\begin{aligned}
    X + y &= a\timesx + a^2\timesb \\
    x &= a(x - a\times b) - y
    \end{aligned}$$

$$\\begin{aligned}
X + y &= (a\\times x) + (a^2\\times b) \\\\
X &= a(x - (a\\times b)) - y
\\end{aligned}$$

#### Exercise 2

Try your best to recreate this equation for a random intercept and
random slop model. If you need help, you can look at the source code.

*y*<sub>*i*</sub> ∼ *N*(*α*<sub>*j*\[*i*\]</sub>+*β*<sub>1</sub>*j*\[*i*\]*x*<sub>1, *i*</sub>+*β*<sub>2</sub>*x*<sub>2, *i*</sub>,*σ*<sub>*y*</sub><sup>2</sup>)

$$\\begin{pmatrix}
 \\alpha_j  \\\\
\\beta_j
\\end{pmatrix} = N\\Big(  \\begin{pmatrix}
 \\mu\_\\alpha  \\\\
\\mu\_\\beta
\\end{pmatrix}, \\begin{pmatrix}
 \\sigma\_{\\alpha}^2 & \\rho\\sigma\_{\\alpha}\\sigma\_{\\beta} \\\\
\\rho\\sigma\_{\\alpha}\\sigma\_{\\beta}  & \\sigma\_{\\beta}^2
\\end{pmatrix}\\Big), \\text{ for } j = 1, \\ldots, J$$

## Resources

That should be more than enough to get you started. Here are a couple of
resources for more information.

-   [List of LaTeX mathematical
    symbols](https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols)

-   \[This detailed LateX math\]
    guide(<http://tug.ctan.org/info/short-math-guide/short-math-guide.pdf>)
