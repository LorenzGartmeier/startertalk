# LaTeX Beamer template 

A beamer theme used within the AIML group at LMU.

## Usage

Copy the project files into your presentation's directory:

`git clone https://gitlab.lrz.de/kiml/lmu_latex_beamer_23.git`

In your presentation, use the beamer document class and tell it to use the LMU theme:

```
\documentclass[fleqn,compress,utf8,aspectratio=169,t]{beamer}
\usetheme{LMU}
```

Make sure that the following files are always in the same direction as your presentation file:


- beamercolorthemelmu.sty
- beamerfontthemelmu.sty
- beamerinnerthemelmu.sty
- beamerinnerthemelmu.sty
- beamerthemeLMU.sty
- recommended-settings.tex
- lmu-example.bib

And that the following files are in the directory figs/:

- lmu_green.pdf
- siegel.pdf
- AIML_Logo.pdf


The frametitle of a slide is currently set by the `\section` command, i.e.,

```
\section{Introduction}
\begin{frame}
    content
\end{frame}
```
will result in a slide with the title ``Introduction''. Creating another slide by 

```
\begin{frame}
    content
\end{frame}
```
directly after the previous command,  will produce another slide with the title ``Introduction''.

## First slide

If you want to incorporate other logos into the headline, go into the beamerinnerthemelmu.sty file and uncomment and change the lines 46-49 accordingly. If the logo is wrongly placed, adjust the \the\paperwidth-28mm accordingly.		


## Citation
Currently, 2 options are supported. Uncomment one of the two Versions in the section "Citation styles" in the preamble of the template.tex file.
(line 16-28)

Version 1: Cite within the text of your slide, which results into sth. like [Mesaoudi-Paul et al. 2020]. For this, use \parencite{} inside your slides
for citation.
Version 2: Footnote cite. Use \footnotemark at the place where you want to cite, and on the bottom of the slide \footnotetext{\cite{Mesaoudi-PaulWB20}}.
You can change the height of the position of the footnote via changing the NUMBER inside \addtobeamertemplate{footnote}{}{\vspace{<NUMBER>ex}}
inside the preamble.

In case your citation does not show up correctly, run in the terminal/shell:

pdflatex templatex.tex
biber template
pdflatex tenplate.tex



