# How I use natbib

I mostly use natbib with authoryear style.

```latex
\usepackage{natbib}
\begin{document}

blablabla

\newpage
\setcitestyle{numbers} % numeric list
\bibliographystyle{jpe} % I use jpe style which follows the authoryear format
\bibliography{foo.bib} % the bib file is foo.bib
\end{document}
```

The example bib file is as follows.

```latex
\begin{filecontents*}{\foo.bib}
@article{alice01,
 author={A. Alice and B. Bob},
 title={?},
 journal={?},
 year=2020,
}
\@article{cindy02,
 author={C. Cindy and D. Dave},
 title={?},
 journal={?},
 year=2020,
}
\end{filecontents*}
```

## Using `\citet`

```latex
\citet{alice01}
```

The result is

```
Alice and Bob (2020)
```

With multiple arguments:

```latex
\citet{alice01,cindy02}
```

The result is

```
Alice and Bob (2020); Cindy and Dave (2020)
```

I rarely use `\citet` with multiple arguments.

## Using `\citep`

```latex
\citep{alice01}
```

The result is

```
(Alice and Bob, 2020)
```

With multiple arguments:

```latex
\citep{alice01,cindy02}
```

The result is

```
(Alice and Bob, 2020; Cindy and Dave, 2020)
```

I often use `\citep` with multiple arguments.

## Using  `\citealp`

Similar to `\citep`. Just without the parentheses.

```latex
\citealp{alice01}
```

```
Alice and Bob, 2020
```

This is often used when I want to say something inside the parentheses. For example,

```
(See, e.g., \citealp{alice01}; \citealp{cindy02})
```

The result is:

```
(See, e.g., Alice and Bob, 2020; Cindy and Dave, 2020)
```

There is also `\citealt` producing `Alice and Bob 2020; Cindy and Dave 2020`.
I have never used it.

## Other

These commands are sometimes used, but not so often as much as the three above.

(1) Use `\citetalias` for custom abbreviation. You need to define the abbreviation first using `\defcitealias{}{}` 

```latex
\defcitealias{alice01}{AB}
% then cite
\citetalias{alice01}\\
% or
\citepalias{alice01}
```

The result is

```
AB 
(AB)
```

One should use the custom abbreviation only if she cites Alice and Bob (2020) more than 10 times in a paragraph.

(2) Use `\citeauthor` and `\citeyear` for author names and year. I usually avoided using it and simply typed the author names and year.  

(3) Here is a [detailed manual](http://merkel.texture.rocks/Latex/natbib.php?lang=en) for natbib. 
