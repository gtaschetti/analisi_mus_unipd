# analisi_mus_unipd

Jupyter notebooks and music files for the course **Analisi delle forme musicali e delle tecniche compositive** — Università degli Studi di Padova, A.Y. 2025/2026.

Music analysis is performed with [crim-intervals](https://github.com/HCDigitalScholarship/intervals), a Python library for computational analysis of Renaissance polyphony.

---

## Requirements

- Python (3.9+)
- [crim-intervals](https://github.com/HCDigitalScholarship/intervals): `pip install crim-intervals`
- pandas, numpy, plotly (installed automatically as crim-intervals dependencies)

---

## Contents

The repository contains Jupyter notebooks for music analysis and a `Music_Files/` folder with scores in **MusicXML** (`.xml`) and **MEI** (`.mei`) format.

Each notebook loads one or more files from `Music_Files/` and performs analysis using crim-intervals. To use a different score, place it in `Music_Files/` and update the `filename` variable in the notebook.

### Notebooks

| Notebook | Description |
|----------|-------------|
| `densita_polifonica_01_base.ipynb` | Minimal polyphonic density analysis with a static bar chart |
| `densita_polifonica_02_avanzato.ipynb` | Full analysis: notes, cadences, lyrics, interactive Plotly charts |
| `estensioni_vocali.ipynb` | Voice range analysis for the Marenzio corpus (Libro IV a 6v, Libro VI a 5v) |

---

## Marenzio Corpus: Sources and Credits

The MEI files in `Music_Files/` with prefix `M_04_6_` and `M_06_5_` come from the
**Marenzio Online Digital Edition (MODE)**, available at
[marenzio.org](http://www.marenzio.org) and on GitHub at
[github.com/marenzio/marenzio.github.io](https://github.com/marenzio/marenzio.github.io).

### Book IV for 6 voices (`M_04_6_`, 15 madrigals)

> Luca Marenzio, *Il quarto libro de' madrigali a sei voci*, edited by Lucia Marchi,
> [MODE – Marenzio Online Digital Edition, 2024](https://marenzio.org/digital-edition/M-04-6.xhtml).

### Book VI for 5 voices (`M_06_5_`, 17 madrigals)

> Luca Marenzio, *Il sesto libro de madrigali a cinque voci*, edited by Daniele Filippi,
> [MODE – Marenzio Online Digital Edition, 2019](https://marenzio.org/digital-edition/M-06-5.xhtml).

### Note on the files

The original files were downloaded from MODE and prepared for use with the libraries used in the notebooks (`music21` and `crim-intervals`). The changes are purely technical and do not affect the musical or editorial content:

1. Removal of the UTF-8 BOM, if present.
2. Expansion of empty `<syl/>` elements to resolve an incompatibility with `music21`.
3. Injection of the title text into an empty `<title/>` element (Book VI only), to resolve an incompatibility with `crim-intervals`.
4. Addition of a `label=` attribute to `<staffDef>` elements, copied from the child `<label>` element: `crim-intervals` reads the attribute, not the child.
5. Propagation of `label=` from labelled `<staffDef>` elements to any unlabelled ones sharing the same staff number (Book IV only, where a second group of `<staffDef>` elements encodes the original chiavette clefs without labels).
6. Addition of an `<instrDef midi.instrnum="0" />` child to each `<staffDef>` that lacks one (Book IV only): without it, `music21` cannot resolve voice names such as *Quinto* and *Sesto* through its instrument database, and `crim-intervals` falls back to generic `Part-N` column names.
7. Re-encoding to ASCII with XML character references for characters outside the ASCII range, to resolve an encoding mismatch in `crim-intervals` on Windows.

---

## License

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You are free to share and adapt the material for any purpose, provided appropriate credit is given.
