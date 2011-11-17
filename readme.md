*this is an adapted version of* [uw-beamer-template](https://github.com/travitch/uw-beamer-template)


This is a Beamer template set up to look pretty decent and have a Univerity of Applied Science Munich theme.  It is, of course, better than the existing Powerpoint templates.

The easiest way to install this theme is to just dump the \*.sty files into the same directory as your tex source.

A minimal Beamer presentation using this template looks something like the following:

```latex
\documentclass{beamer}

\usetheme{Muenchen}
\begin{document}
%% Slides
\end{document}
```

A few of the theme's options:

- nav   - This option includes a navigation bar in the lower-right corner of each slide
- white - This option changes the color scheme to black-on-white for projectors with poor color balance
- useinfofooter - This option adds the 'default' infolines footer.

Options are specified as:

```latex
  \usetheme[white]{Muenchen}
```

Other suggested packages:
- tikz (pgf, for diagrams)
- listings (for source code listings)
- fontspec (if using xetex)


Meta
---

original Release: [uw-beamer-template](https://github.com/travitch/uw-beamer-template)
Adapted: November 2011
Public Domain

Extra
-----

Here is a very handy snippet of TeX to stick at
the beginning of your presentation (after \begin{document}):

```latex
\newcommand*{\alphabet}{ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz}
\newlength{\highlightheight}
\newlength{\highlightdepth}
\newlength{\highlightmargin}
\setlength{\highlightmargin}{2pt}
\settoheight{\highlightheight}{\alphabet}
\settodepth{\highlightdepth}{\alphabet}
\addtolength{\highlightheight}{\highlightmargin}
\addtolength{\highlightdepth}{\highlightmargin}
\addtolength{\highlightheight}{\highlightdepth}
\newcommand*{\Highlight}{\rlap{\textcolor{HighlightBackground}{\rule[-\highlightdepth]{\linewidth}{\highlightheight}}}}
```

HighlightBackground is defined by the Wisconsin theme.  This
snippet allows you to include source code listings in the
following way:

```latex
  \lstinputlisting[language=C,moredelim={**[il][\Highlight]{@}}]{file.c}
```

Note the moredelim option; with this option and the preceeding
declarations, prefixing a line in file.c will highlight the line.

