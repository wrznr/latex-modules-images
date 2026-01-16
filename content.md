layout: true
  
<div class="my-header"></div>

<div class="my-footer">
  <table>
    <tr>
      <td style="text-align:right">Sächsische Landesbibliothek – Staats- und Universitätsbibliothek</td>
      <td>16. Januar 2026</td>
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
      <td style="font-size:8pt"><b>16. Januar 26</b></td>
    </tr>
    <tr>
      <td style="font-size:8pt">LaTeX-Modul: Bilder</td>
    </tr>
  </table>
</div>

---

class: title-slide
count: false

# Bilder in LaTeX integrieren und generieren

---

# Übersicht

1. Grundlagen der Bildeinbindung
2. Bildqualität: Pixel- vs. Vektorgrafiken
3. Anpassung der Bildplatzierung
4. Bilder generieren mit TikZ

- Vereinfachung komplexer Ideen
- Erhöhtes Leserengagement
- Klarere Unterstützung von Argumenten
- Verbesserte professionelle Präsentation
- Besseres Verständnis

---

class: part-slide
count: false

# Grundlagen der Bildeinbindung

---

# Importieren von Bildern in LaTeX

- Zentrales Paket: `graphicx`
  ```latex
  \usepackage{graphicx}
  \includegraphics[width=\linewidth]{bild.ext}
  ```

- Gängige Optionen:
  - `width` (Breite), `height` (Höhe), `scale` (Skalierung), `angle` (Winkel)

---

# Importieren von Bildern in LaTeX

```latex
\documentclass{standalone}
\usepackage{graphicx}
\begin{document}
\includegraphics[width=\linewidth]{bild.ext}
\end{document}
```

- Fügen Sie Ihre eigene `.png`-, `.jpg`- oder `.pdf`-Datei ein.
- Verwenden Sie **relative Dateipfade** für Portabilität.

---

class: part-slide
count: false

# Bildqualität: Pixel- vs. Vektorgrafiken

---

# Bildarten

1. **Pixelbasiert (Rastergrafiken)**
   - Auflösungsabhängig
   - Formate: `.png`, `.jpg`

2. **Vektorbasiert**
   - Skalierbar ohne Qualitätsverlust
   - Formate: `.pdf`, `.svg`

| Typ         | Beispielformat | Anwendungsfall         |
|-------------|----------------|------------------------|
| Pixelbasiert| `.jpg`, `.png` | Fotos, Screenshots     |
| Vektorbasiert| `.svg`, `.pdf`| Diagramme, Illustrationen|

---

# Beispiel: Pixel- vs. Vektorgrafiken

![Niedrig aufgelöstes Bild](img/low-res-example.jpg)  
*Niedrig aufgelöstes Pixelbild*

![Hochauflösendes Bild](img/high-res-example.jpg)  
*Hochauflösendes Pixelbild*

![Vektorbild](img/vector-example.svg)  
*Scharfes und skalierbares Vektorbild*

---

class: part-slide
count: false

# Anpassung der Bildplatzierung

---

# Bilder in eine `figure`-Umgebung einbetten

```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.8\linewidth]{bild.ext}
    \caption{Ein Beispielbild.}
    \label{fig:beispiel}
\end{figure}
```

- Standardmethode zur Handhabung von Bildern in wissenschaftlichen Arbeiten
- Verwenden Sie `[h]`, `[t]`, `[b]`, `[p]` oder `!` für die Platzierung.
- Fügen Sie Bildunterschriften und Labels für Querverweise hinzu.

---

# Erstellen eines Abbildungsverzeichnisses in LaTeX

```latex
\documentclass{report}
   \usepackage{graphicx}
   \begin{document}
   \tableofcontents
   \listoffigures
   \chapter{Einleitung}
   \begin{figure}[h]
       \centering
       \includegraphics[width=\linewidth]{bild.ext}
       \caption{Eine Beispielabbildung.}
   \end{figure}
   \end{document}
``` 

- Übersicht aller Abbildungen im Dokument
- Meistens nach dem Inhaltsverzeichnis platziert

---

# Textumflossene Bilder

```latex
\usepackage{wrapfig}
\begin{wrapfigure}{r}{0.4\textwidth}
\centering
\includegraphics[width=\linewidth]{bild.ext}
\caption{Ein Beispielbild.}
\label{fig:wrap}
\end{wrapfigure}
\blindtext
```

- Erstellt visuell ansprechende Layouts.
- Spart Platz in Dokumenten.
- Häufig verwendet in Abschlussarbeiten, Berichten und Artikeln.

---

# Kombinieren mehrerer Bilder

```latex
\usepackage{subcaption}
\begin{figure}[h]
    \begin{subfigure}[b]{0.45\linewidth}
        \includegraphics[width=\linewidth]{bild1.ext}
        \caption{Bild 1}
    \end{subfigure}
    \hfill
    \begin{subfigure}[b]{0.45\linewidth}
        \includegraphics[width=\linewidth]{bild2.ext}
        \caption{Bild 2}
    \end{subfigure}
\end{figure}
```

- Best-Practice-Lösung zum Kombinieren mehrerer Bilder in einer einzigen Abbildung
- Automatische Unterindizierung; verwenden Sie separate Labels.

---

class: part-slide
count: false

# Bilder generieren mit TikZ

---

# Was ist TikZ?

- Eine LaTeX-Bibliothek zum Zeichnen von Vektorgrafiken.
- Häufige Anwendungen:
  - Diagramme
  - Geometrische Formen
  - Flussdiagramme
- R spricht TikZ (via `TikZDevice`)!
```R
tikz('tikz-example.tex',
width = 3.25, height = 3.25)
plot(1, 1, main = 'Hallo \\TeX !')
dev.off()
```
- LLMs sprechen TikZ!

---

## Beispiel: Zeichnen mit TikZ

```latex
\usepackage{tikz}
\begin{tikzpicture}
    \draw[blue, thick] (0,0) circle (1cm);
    \draw[red, thick] (0,0) -- (1,1);
\end{tikzpicture}
```

*Erzeugt diese Grafik:*

![TikZ Beispiel](img/vector-example.svg)

---

class: part-slide

# Vielen Dank für Ihre Aufmerksamkeit!

<center>
<a href="https://wrznr.github.io/latex-module-images/">wrznr.github.io/latex-module-images</a>
</center>
