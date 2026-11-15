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

---

## 3. Instrucciones de Ejecución y Reproducibilidad

### Opción A: Ejecución en Google Colab (Recomendada)
1. Abra el archivo `notebooks/Simulacion_HMM_Cadena_Suministro.ipynb` y cárguelo en Google Colab.
2. Ejecute todas las celdas en orden (`Entorno de ejecución > Ejecutar todas`).
3. El generador pseudoaleatorio maestro `np.random.default_rng(42)` reproducirá exactamente las métricas reportadas en el artículo.

### Opción B: Ejecución Local

    git clone [https://github.com/josehilariolopezr/HMM-Supply-Chain-Resilience.git](https://github.com/josehilariolopezr/HMM-Supply-Chain-Resilience.git)
    cd HMM-Supply-Chain-Resilience
    pip install -r requirements.txt
    jupyter notebook notebooks/Simulacion_HMM_Cadena_Suministro.ipynb

---

## 4. Resumen de Resultados Principales ($N = 100, T = 60, \text{seed} = 42$)

| Escenario Experimental | Modelo | Exactitud Media | Desv. Estándar | Intervalo de Confianza ($IC_{95\%}$) |
| :--- | :--- | :---: | :---: | :---: |
| **E1: Nominal Discreto** | **HMM (Viterbi)** | **0,7817** | 0,0884 | `[0,7643 ; 0,7990]` |
| **E1: Nominal Discreto** | Baseline (Umbral) | 0,7350 | 0,0635 | `[0,7226 ; 0,7474]` |
| **E2: Alta Perturbación** | **HMM (Viterbi)** | **0,5223** | 0,0756 | `[0,5075 ; 0,5371]` |
| **E2: Alta Perturbación** | Baseline (Umbral) | 0,5277 | 0,0632 | `[0,5153 ; 0,5401]` |
| **E3: Continuo Gaussiano** | **HMM (Viterbi)** | **0,9590** | 0,0309 | `[0,9529 ; 0,9651]` |
| **E3: Continuo Gaussiano** | Baseline (Umbral) | 0,9417 | 0,0349 | `[0,9348 ; 0,9485]` |
