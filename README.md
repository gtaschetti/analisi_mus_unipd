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

---

## License

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You are free to share and adapt the material for any purpose, provided appropriate credit is given.
