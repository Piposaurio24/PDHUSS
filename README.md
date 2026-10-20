# Lake Grey Level Recovery: Combining Satellite Altimetry and Artificial Intelligence

*Recuperación del Nivel del Lago Grey: Combinando Herramientas de Altimetría Satelital e Inteligencia Artificial*

Research project developed for the **Programa de Honor 2025** (Vicerrectoría de Investigación y Doctorados, Universidad San Sebastián, Chile).

**Authors**
- Agustín Tardones-Pezo, Civil Engineering, Facultad de Ingeniería, Tres Pascualas
- Lien Rodríguez-López, Unidad Académica



## Overview

Depending on how well monitoring stations are maintained, and on interruptions in data collection, hydrological records can have missing data ranging from close to 0% up to 40% or more [1]. Satellite altimetry provides objective, continuous and high-precision measurements that can feed artificial intelligence models [2], and Machine Learning models can produce reliable estimates of missing values from hydroclimatic information.

This project trains and compares neural network models that predict the water level of **Lake Grey** (Región de Magallanes, Chile).

## Objective

Build a model able to predict Lake Grey water levels with enough reliability from physical variables, in order to verify and validate the use of these technologies on the country's government lake databases for estimating lost data.

## Methodology

1. Obtain the physical characteristics data for Lake Grey from the **DGA** (Dirección General de Aguas) database.
2. Sort and process the data in **Python**, then split it into training and test sets for the neural network models.
3. Plot the predictions against the real values.
4. Calculate performance metrics and compare the results.

**Models compared**

- GRU (Gated Recurrent Unit)
- Simple LSTM
- Bidirectional GRU
- Bidirectional LSTM

**Metrics:** RMSE, MAE, RSR and MAPE.

## Results

| Model | RMSE | MAE | RSR | MAPE |
|---|---|---|---|---|
| **GRU** | **0.0635** | **0.0401** | **0.1055** | **0.08%** |
| Simple LSTM | 0.0742 | 0.0499 | 0.1234 | 0.10% |
| Bidirectional GRU | 0.0648 | 0.0415 | 0.1077 | 0.08% |
| Bidirectional LSTM | 0.0789 | 0.0516 | 0.1313 | 0.10% |

RMSE and MAE are in metres of lake level.

## Conclusions

- The best model in this study is the **GRU**, with an accuracy of 99.92% (MAPE: 0.08%) and an average error of 6.35 cm, outperforming the LSTM and the bidirectional variants.
- The simpler architectures performed better than the more complex ones, which is attributed to how efficiently the models use the parameters they are given.
- All models performed quite well, which supports the effectiveness of Machine Learning models for predicting lake levels in Chile.

## Repository contents

```
.
├── notebook.ipynb     # analysis and model training (rename to match your file)
├── docs/
│   └── poster.pdf     # Programa de Honor 2025 poster
└── README.md
```

## Running the notebook

1. Open the notebook in Google Colab (or Jupyter).
2. Make sure the Lake Grey data from the DGA is available to the notebook.
3. Run all cells to process the data, train the models and reproduce the comparison plots and metrics.

## References

1. J. K. Yimam, T. K. Kassa and A. D. Mengistu, "Assessment of Missing Hydrological Data and its Impact on River Flow Simulation in the Upper Awash Basin, Ethiopia," *Proceedings of the International Association of Hydrological Sciences*, vol. 384, pp. 135–142, 2021.
2. J. Kleinherenbrink, C. D. D. Kittel, R. Scharroo and R. Scharroo, "Satellite Altimetry for Inland Water Monitoring: Capabilities, Limitations, and Perspectives," *Remote Sensing*, vol. 16, no. 7, art. 1181, 2024.
