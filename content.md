layout: true
  
<div class="my-header"></div>

<div class="my-footer">
  <table>
    <tr>
      <td style="text-align:right">Sächsische Landesbibliothek – Staats- und Universitätsbibliothek</td>
      <td>28th November 2024</td>
      <td style="text-align:right"><a href="https://www.slub-dresden.de/">www.slub-dresden.de</a></td>
    </tr>
    <tr>
      <td style="text-align:right">Referat 4.3</td>
      <td />
    </tr>
  </table>
</div>

<div class="my-title-footer">
  <table>
    <tr>
      <td style="text-align:left"><b>Kay-Michael Würzner</b></td>
    </tr>
    <tr>
      <td style="text-align:left">Referat 4.3</td>
    </tr>
    <tr>
      <td style="font-size:8pt"><b>28th November 24</b></td>
    </tr>
    <tr>
      <td style="font-size:8pt">Latex Module: Images</td>
    </tr>
  </table>
</div>

---

class: title-slide
count: false

# Integrating and Generating Images in LaTeX

---

# Overview

1. Basics of image integration
2. Image quality: pixel vs. vector graphics
3. Customizing image placement
4. Generating images with TikZ

- Simplification of complex ideas
- Increased reader engagement
- Clearer support for arguments
- Enhanced professional presentation
- Improved comprehension and retention

---

class: part-slide
count: false

# Basics of image integration

---

# Importing Images in LaTeX

- Central package: `graphicx`
  ```latex
  \usepackage{graphicx}
  \includegraphics[width=\linewidth]{example-image}
  ```

- Common options:
  - `width`, `height`, `scale`, `angle`

---

# Importing Images in LaTeX

```latex
\documentclass{standalone}
\usepackage{graphicx}
\begin{document}
\includegraphics[width=\linewidth]{image.ext}
\end{document}
```

- Insert your own `.png`, `.jpg`, or `.pdf` file.
- Use **relative file paths** for portability.

---

class: part-slide
count: false

# Image Quality: Pixel vs. Vector Graphics

---

# Types of Images

1. **Pixel-Based (Raster Graphics)**
   - Resolution-dependent
   - Formats: `.png`, `.jpg`

2. **Vector-Based**
   - Scalable without loss of quality
   - Formats: `.pdf`, `.svg`

| Type        | Example Format | Use Case          |
|-------------|----------------|------------------------|
| Pixel-Based | `.jpg`, `.png` | Photos, screenshots   |
| Vector-Based| `.svg`, `.pdf` | Diagrams, illustrations|

---

# Example: Pixel vs. Vector Graphics

![Low-Res Image](img/low-res-example.jpg)  
*Low-resolution pixel image*

![High-Res Image](img/high-res-example.jpg)  
*High-resolution pixel image*

![Vector Image](img/vector-example.svg)  
*Sharp and scalable vector image*

---

class: part-slide
count: false

# Customizing Image Placement

---

# Wrapping Images in a `figure`

```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.8\linewidth]{image.ext}
    \caption{An example image.}
    \label{fig:example}
\end{figure}
```

- Standard way of image handling in scientific works
- Use `[h]`, `[t]`, `[b]`, `[p]`, or `!` for placement.
- Add captions and labels for cross-referencing.

---

# Creating a List of Figures in LaTeX

```latex
\documentclass{report}
   \usepackage{graphicx}
   \begin{document}
   \tableofcontents
   \listoffigures
   \chapter{Introduction}
   \begin{figure}[h]
       \centering
       \includegraphics[width=\linewidth]{example-image}
       \caption{An example figure.}
   \end{figure}
   \end{document}
``` 

- Overview of all figures in the document
- Usually after table of contents

---

# Wrapping figures text

```latex
\usepackage{wrapfig}
\begin{wrapfigure}{r}{0.4\textwidth}
\centering
\includegraphics[width=\linewidth]{example-image}
\caption{An example image.}
\label{fig:wrap}
\end{wrapfigure}
\blindtext
```

- Creates visually appealing layouts.
- Saves space in documents.
- Commonly used in theses, reports, and articles.

---

# Combining Multiple Images

```latex
\usepackage{subcaption}
\begin{figure}[h]
    \begin{subfigure}[b]{0.45\linewidth}
        \includegraphics[width=\linewidth]{image1}
        \caption{Image 1}
    \end{subfigure}
    \hfill
    \begin{subfigure}[b]{0.45\linewidth}
        \includegraphics[width=\linewidth]{image2}
        \caption{Image 2}
    \end{subfigure}
\end{figure}
```

- Best-practice solution for combining multiple images in a single figure
- Better than a table!
- Automatic sub indexing, use separate labels.

---

class: part-slide
count: false

# Generating Images with TikZ

---

# What is TikZ?

- A LaTeX library for drawing vector graphics.
- Common applications:
  - Diagrams
  - Geometric shapes
  - Flowcharts
- R speaks TikZ (via `tikzDevice`)!
```R
tikz('tikz-example.tex',
width = 3.25, height = 3.25)
plot(1, 1, main = 'Hello \\TeX !')
dev.off()
```
- ChatGPT speaks TikZ!

---

## Example: Drawing with TikZ

```latex
\usepackage{tikz}
\begin{tikzpicture}
    \draw[blue, thick] (0,0) circle (1cm);
    \draw[red, thick] (0,0) -- (1,1);
\end{tikzpicture}
```

*Generates this graphic:*

![TikZ Example](img/vector-example.svg)

---

class: part-slide

# Many thanks for your attention!

<center>
<a href="https://wrznr.github.io/latex-module-images/">wrznr.github.io/latex-module-images</a>
</center>
