# SoccerDiffusion

⚽ **Modeling football possession dynamics using fractional Brownian motion**

> **Team project** developed for the course Project III, Bachelor's Degree in Data Science (Universitat Politècnica de València). Original repository: [ghursan/SoccerDiffusion](https://github.com/ghursan/SoccerDiffusion).

This project explores how ball-movement patterns in football can be modeled with fractional Brownian motion (fBm) and characterized through the **Hurst exponent (H)**, a statistical measure of persistence in time series.

The goal is to estimate the Hurst exponent from possession sequences and to understand how it changes in response to match events such as goals, red cards or defensive pressure. The project combines synthetic data generation, machine learning and real match analysis to provide new tactical insights for football analytics.

---

## Project highlights

- **Synthetic data generation:** 50,000 football possessions generated with fractional Brownian motion, each labeled with a known Hurst exponent.
- **Feature engineering:** movement features (speed, acceleration, angles, etc.) extracted from each possession.
- **Machine learning:** XGBoost, Random Forest, Linear Regression, MLP and LSTM models trained to predict the Hurst exponent from possession features.
- **Event analysis:** the best-performing model (XGBoost) applied to real FC Barcelona matches from the 2019/2020 LaLiga season (StatsBomb open data), analysing how *H* changes in response to:
  - goals
  - red cards
  - substitutions
  - defensive pressure
- **Web visualization:** a lightweight Flask website that presents the project and its results.

## Repository structure

```text
SoccerDiffusion/
├── data/
│   └── posesiones_sinteticas.csv     # Synthetic possessions used for training and evaluation
├── notebooks/
│   ├── artificial_data.ipynb         # Synthetic data generation and model training
│   ├── codigo_proyecto.ipynb         # Real match processing and event analysis
│   └── pruebas*.ipynb                # Exploratory notebooks
├── information/
│   ├── Statsboms PDF/                # StatsBomb data documentation
│   ├── M1-SOCCER DIFFUSION.pdf       # Milestone 1 presentation
│   ├── M2-SOCCER DIFFUSION.pdf       # Milestone 2 report
│   ├── Final_memory.pdf              # Final project report
│   └── *.pdf                         # Reference papers
├── web/
│   ├── app.py                        # Flask application
│   ├── templates/                    # HTML templates
│   └── static/                       # CSS, images and videos
├── requirements.txt
└── README.md
```

## How to run

1. Clone the repository:
   ```bash
   git clone https://github.com/ivangarciadonderis/SoccerDiffusion.git
   cd SoccerDiffusion
   ```
2. Install the dependencies (a virtual environment is recommended):
   ```bash
   pip install -r requirements.txt
   ```
3. Open the notebooks in `notebooks/`. The main ones are:
   - `artificial_data.ipynb`: synthetic possessions and model training.
   - `codigo_proyecto.ipynb`: application to real StatsBomb matches and event analysis.

### Website

```bash
cd web
python app.py
```

Then open `http://127.0.0.1:5000` in your browser.

## Documentation

Methodology, results and evaluation are described in:

- [`information/M1-SOCCER DIFFUSION.pdf`](information/M1-SOCCER%20DIFFUSION.pdf)
- [`information/M2-SOCCER DIFFUSION.pdf`](information/M2-SOCCER%20DIFFUSION.pdf)
- [`information/Final_memory.pdf`](information/Final_memory.pdf)

## Data

Real match data comes from [StatsBomb Open Data](https://github.com/statsbomb/open-data), accessed with the `statsbombpy` package.

## License

This project is licensed under the [MIT License](LICENSE).
