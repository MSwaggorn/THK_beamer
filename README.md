# TH Köln Beamer Template

A professional LaTeX Beamer presentation template designed for TH Köln (Technische Hochschule Köln).

## Features

- **Custom Color Scheme**: TH Köln brand colors (Red, Orange, Purple)
- **Professional Layout**: Clean header bar and footer with logo
- **Multiple Slide Types**: Title, bullet points, figures, side-by-side layouts
- **German Language Support**: Configured for German presentations
- **Modular Structure**: Clean separation of configuration and content
- **Professional Typography**: Properly sized headings, text, and captions
- **4-Level Bullet Points**: Color-coded indentation levels
- **Bibliography Support**: Biblatex with Biber backend
- **Cross-referencing**: Cleveref package for intelligent references

## Project Structure

```
THK_beamer/
├── main.tex                    # Main presentation file (edit this for content)
├── references.bib              # Bibliography file
├── config/                     # Configuration files
│   ├── packages.tex           # Package imports
│   ├── colors.tex             # Color definitions
│   ├── variables.tex          # Customizable variables
│   ├── fonts.tex              # Font size definitions
│   ├── theme.tex              # Beamer theme customization
│   └── slide-types.tex        # Slide type helpers and examples
└── images/                     # Image directory
    └── TH_Koeln_Logo.svg.png  # University logo
```

## Quick Start

1. **Customize Your Presentation**
   Edit `config/variables.tex` to set:
   - Presentation title and subtitle
   - Your name
   - Professor/advisor names
   - Date

2. **Add Content**
   Edit `main.tex` to add your slides

3. **Compile**
   ```bash
   pdflatex main.tex
   biber main
   pdflatex main.tex
   pdflatex main.tex
   ```

   Or use latexmk:
   ```bash
   latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode" main.tex
   ```

## Slide Types

### 1. Title Slide
```latex
\begin{frame}[plain]
\titlepage
\end{frame}
```

### 2. Bullet Points
```latex
\begin{frame}
\frametitle{Your Title}
\begin{itemize}
    \item Level 0 (black)
    \begin{itemize}
        \item Level 1 (red)
        \begin{itemize}
            \item Level 2 (orange)
            \begin{itemize}
                \item Level 3 (purple)
            \end{itemize}
        \end{itemize}
    \end{itemize}
\end{itemize}
\end{frame}
```

### 3. Figure Slide
```latex
\begin{frame}
\frametitle{Figure Title}
\begin{figure}
    \centering
    \includegraphics[width=0.7\textwidth]{image-name}
    \caption{Your caption}
\end{figure}
\end{frame}
```

### 4. Side-by-Side
```latex
\begin{frame}
\frametitle{Title}
\begin{columns}[T]
    \begin{column}{0.48\textwidth}
        % Left content
    \end{column}
    \begin{column}{0.48\textwidth}
        % Right content
    \end{column}
\end{columns}
\end{frame}
```

### 5. Side-by-Side with Subheadings
```latex
\begin{frame}
\frametitle{Main Title}
\begin{columns}[T]
    \begin{column}{0.48\textwidth}
        \subheading{Left Title}
        % Left content
    \end{column}
    \begin{column}{0.48\textwidth}
        \subheading{Right Title}
        % Right content
    \end{column}
\end{columns}
\end{frame}
```

## Customization

### Colors
Edit `config/colors.tex` to change the color scheme:
```latex
\definecolor{THRed}{RGB}{207,24,32}
\definecolor{THOrange}{RGB}{236,101,37}
\definecolor{THPurple}{RGB}{175,54,140}
```

### Font Sizes
Edit `config/fonts.tex` to adjust text sizes:
- Heading: 26pt
- Sub-heading: 22pt
- Normal text: 18pt
- Caption: 16pt
- Footnote: 10pt

### Variables
Edit `config/variables.tex` for presentation metadata

## Requirements

- LaTeX distribution (TeX Live, MiKTeX, etc.)
- Biber (for bibliography)
- Required packages (all included in standard distributions):
  - beamer
  - babel (ngerman)
  - graphicx
  - xcolor
  - tikz
  - booktabs
  - biblatex
  - hyperref
  - cleveref

## License

This template is free to use and modify for academic presentations.
