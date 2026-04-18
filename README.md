# 🔍 Detección de Fraude en Bitcoin con Elliptic Dataset

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![GNN](https://img.shields.io/badge/GNN-GCN%20%7C%20GAT-blueviolet)](https://pytorch-geometric.readthedocs.io/)
![Visitas](https://komarev.com/ghpvc/?username=SebastianDeghi&color=blue&style=flat)

### 👥 Colaboradores: **Sofía Bobbiesi Bender, Mildre Cepeda y Dalma Márquez.**

***

## 📝 Descripción General
Análisis exploratorio y clasificación de transacciones fraudulentas en la red Bitcoin utilizando el dataset Elliptic.

***

## 📁 Estructura del Proyecto

La organización de los archivos en este repositorio es la siguiente:

```
elliptic-bitcoin-fraud-detection/
├── EllipticDataset_DataAnalysis.ipynb   # Notebook principal con EDA, curación y modelos
├── requirements.txt                     # Dependencias de Python para reproducir el entorno
├── LICENSE                              # Licencia MIT
├── .gitignore                           # Archivos y carpetas ignorados por Git
└── README.md                            # Este archivo
```

***

## 📊 Descripción del Dataset

El conjunto de datos **Elliptic**, desarrollado por la empresa Elliptic, modela una **red temporal de transacciones de Bitcoin** y es uno de los más completos para la investigación en detección de lavado de dinero (AML).

- **Nodos:** 203,769 transacciones (cada una con un sello temporal).
- **Aristas:** 234,355 flujos de pago dirigidos entre transacciones.
- **Características:** 165 variables numéricas por nodo, que incluyen:
    - **Locales (0-93):** Monto total, número de entradas/salidas, tiempo promedio entre operaciones, etc.
    - **Agregadas (94-153):** Estadísticas (media, max, min, std) de los nodos vecinos.
    - **Temporales (154-164):** Información temporal local y del entorno.
- **Etiquetas de Clase:**
    - `0` = Lícita
    - `1` = Ilícita
    - `2` = Desconocida

***

## 🚀 Modelos de Clasificación Implementados

Se entrenaron y compararon un total de **8 modelos**, incluyendo enfoques tradicionales, de aprendizaje profundo y basados en grafos.

| Tipo de Modelo | Algoritmo | Rendimiento (F1-score) |
| :--- | :--- | :--- |
| **Tabular (Tradicional)** | Regresión Logística | ~0.88 |
| | Random Forest | ~0.93 |
| | SVM (RBF) | ~0.87 |
| | Árbol de Decisión | ~0.85 |
| | **XGBoost** | **~0.94 (⭐ Mejor)** |
| **Red Neuronal** | MLP (Perceptrón Multicapa) | ~0.89 |
| **Grafos (GNNs)** | GCN (Graph Convolutional Network) | ~0.85 |
| | GAT (Graph Attention Network) | ~0.86 |

**Conclusión Clave:** Los modelos basados en atributos individuales de los nodos (especialmente **XGBoost**) superaron a los modelos de grafos, lo que sugiere que, para este conjunto de datos, la información de las características propias de las transacciones es más relevante que la topología de la red para la detección de fraude.

***

## 🔧 Instalación y Uso

Sigue estos pasos para clonar el repositorio, configurar el entorno y ejecutar el análisis en tu máquina local.

### 1. Clonar el repositorio

Abre tu terminal y ejecuta:
```bash
git clone https://github.com/SebastianDeghi/elliptic-bitcoin-fraud-detection.git
cd elliptic-bitcoin-fraud-detection
```

### 2. Crear y activar un entorno virtual (recomendado)

- En **Windows**:
  ```bash
  python -m venv venv
  venv\Scripts\activate
  ```
- En **macOS/Linux**:
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

### 3. Instalar dependencias

Con el entorno virtual activo, instala los paquetes necesarios:
```bash
pip install -r requirements.txt
```

**Nota:** El archivo `requirements.txt` incluye librerías como `torch`, `torch-geometric`, `pandas`, `scikit-learn`, `xgboost`, `umap-learn`, entre otras.

### 4. Ejecutar el notebook

Finalmente, lanza Jupyter Notebook para abrir el archivo principal:
```bash
jupyter notebook EllipticDataset_DataAnalysis.ipynb
```

***

## 📚 Referencias y Recursos

- **Artículo Académico:** Weber, M. et al. (2019). *Anti-Money Laundering in Bitcoin: Experimenting with Graph Convolutional Networks for Financial Forensics*. [arXiv:1908.02591](https://arxiv.org/abs/1908.02591).
- **Dataset:** [Elliptic Bitcoin Dataset en Kaggle](https://www.kaggle.com/datasets/ellipticco/elliptic-data-set).
- **Librería de Datasets:** [`torch-geometric` EllipticBitcoinDataset](https://pytorch-geometric.readthedocs.io/en/latest/generated/torch_geometric.datasets.EllipticBitcoinDataset.html).

***

## 📄 Licencia

Este proyecto está bajo la licencia **MIT**. Para más detalles, consulta el archivo [`LICENSE`](LICENSE) en la raíz del repositorio.

***

## 🙏 Agradecimientos

- A la empresa **Elliptic** por crear y publicar este valioso conjunto de datos para la investigación.
- A toda la comunidad de código abierto por las herramientas que hicieron posible este análisis (`pytorch`, `pytorch-geometric`, `scikit-learn`, `xgboost`, etc.).

***

## 👤 Autor
Sebastián Deghi
- GitHub: [@SebastianDeghi](https://github.com/SebastianDeghi)
- LinkedIn: [@sebastian-deghi](https://www.linkedin.com/in/sebastian-deghi/)
- Google Scholar: [@Sebastian E. Deghi](https://scholar.google.com/citations?user=3Nq5hTIAAAAJ&hl=en)