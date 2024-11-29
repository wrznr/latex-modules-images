layout: true
  
<div class="my-header"></div>

<div class="my-footer">
  <table>
    <tr>
      <td style="text-align:right">Sächsische Landesbibliothek – Staats- und Universitätsbibliothek</td>
      <td>Date</td>
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
5. Advanced topics

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

# Image Quality: Pixel vs. Vector Graphics

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

---

![Vector Image](img/vector-example.svg)  
*Sharp and scalable vector image*

---

class: part-slide

# Many thanks for your attention!

<center>
<a href="https://wrznr.github.io/latex-module-images/">wrznr.github.io/latex-module-images</a>
</center>
