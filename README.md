# Modelado Estocástico de la Resiliencia en Cadenas de Suministro mediante Modelos Ocultos de Markov (HMM)

[![Python](https://img.shields.io/badge/Python-3.11.9-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Reproducibility](https://img.shields.io/badge/Seed-42%20(Determinista)-orange.svg)]()

**Institución Universitaria Digital de Antioquia (IU Digital)**  
**Facultad de Ingeniería y Ciencias Agropecuarias — Ingeniería de Software y Datos**  
**Asignatura:** Simulación (`PREICA2602B020045`) | **Grupo No. 45**  
**Autores:** José Hilario López Rojas & Dennyn Pandales Pérez  
**Docente:** Prof. Julián Andrés Loaiza  

---

## 1. Descripción del Proyecto
Este repositorio contiene la implementación modular, reproducible y auditada de un **Modelo Oculto de Markov (HMM)** diseñado para inferir el estado operativo latente de una cadena de suministro terrestre ($s_1$: *Operación Normal*, $s_2$: *Retraso Operativo*, $s_3$: *Colapso Logístico*) a partir de observaciones secuenciales de tiempos de entrega (*lead times*).

El proyecto implementa desde cero en espacio logarítmico los tres algoritmos fundamentales de Rabiner (1989):
- **Evaluación:** Algoritmo *Forward* ($\alpha_t$).
- **Decodificación Óptima:** Algoritmo de *Viterbi* ($\delta_t, \psi_t$).
- **Aprendizaje No Supervisado:** Algoritmo *Baum-Welch* (EM).

---

## 2. Estructura del Repositorio
```text
HMM-Supply-Chain-Resilience/
├── README.md
├── requirements.txt
├── notebooks/
│   └── Simulacion_HMM_Cadena_Suministro.ipynb
├── results/
│   ├── tabla3_resultados_montecarlo.csv
│   ├── fig1_diagrama_flujo.png
│   ├── fig2_comparacion_escenarios.png
│   ├── fig3_dinamica_temporal.png
│   └── fig4_matrices_confusion.png
└── docs/
    └── Lopez_Jose_Hilario_y_Pandales_Dennyn.pdf
