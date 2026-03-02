# analisi_mus_unipd

Jupyter notebooks and music files for the course **Analisi delle forme musicali e delle tecniche compositive** — Università degli Studi di Padova, A.Y. 2025/2026.

Music analysis is performed with [crim-intervals](https://github.com/HCDigitalScholarship/intervals), a Python library for computational analysis of Renaissance polyphony.

---

## Requirements

- Python (3.9+)
- [crim-intervals](https://github.com/HCDigitalScholarship/intervals): `pip install crim-intervals`
- pandas, numpy, plotly (installed automatically as crim-intervals dependencies)

---

## Repository structure

```
analisi_mus_unipd/
├── Music_Files/                  # MusicXML scores (.xml)
│   └── Marenzio_o_voi.xml
├── Densita_polifonica_ver_02.ipynb
└── README.md
```

---

## Notebooks

### `Densita_polifonica_ver_02.ipynb` — Polyphonic density analysis

Loads a MusicXML score and produces two interactive Plotly charts:

- **Voice activity** — horizontal bar chart showing when each voice is active, with a measure ruler and cadence markers overlaid
- **Sounding voices** — bar chart of the number of simultaneously active voices over the course of the piece

Additional data extracted per event: notes, durations, lyrics, and cadences (type, tone, CVFs).


## Music files

Scores are in **MusicXML** format (`.xml`). Place any additional file in the `Music_Files/` folder and update the `filename` variable in the notebook accordingly.

---

## License

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You are free to share and adapt the material for any purpose, provided appropriate credit is given.
