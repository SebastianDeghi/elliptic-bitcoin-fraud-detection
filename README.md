[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# 🔍 Detección de Fraude en Bitcoin con Elliptic Dataset

## 📝 Descripción
Análisis exploratorio y clasificación de transacciones fraudulentas en la red Bitcoin utilizando el dataset Elliptic.

## 📊 Dataset
- **Fuente:** Elliptic Bitcoin Dataset (torch-geometric)
- **Tamaño:** 49 snapshots temporales
- **Características:** 165 features por nodo
- **Clases:** Lícito, Ilícito, Desconocido

## 🚀 Modelos Implementados
- Regresión Logística
- Random Forest
- SVM
- XGBoost (⭐ Mejor rendimiento: F1-score ~0.94)
- MLP
- GCN (Graph Convolutional Network)
- GAT (Graph Attention Network)

## 📁 Estructura del Proyecto
elliptic-bitcoin-fraud-detection/
├── EllipticDataset_DataAnalysis.ipynb # Notebook principal
├── README.md # Este archivo
├── requirements.txt # Dependencias
└── .gitignore # Archivos ignorados

## 🔧 Instalación y Uso

### 1. Clonar el repositorio
```bash
git clone https://github.com/SebastianDeghi/elliptic-bitcoin-fraud-detection.git
cd elliptic-bitcoin-fraud-detection
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt # Dependencias
jupyter notebook EllipticDataset_DataAnalysis.ipynb

## 📈 Resultados Principales
Modelo	F1-score
XGBoost	0.94
Random Forest	0.93
GCN	~0.85

## 📚 Referencias
Weber et al. (2019). Anti-Money Laundering in Bitcoin.
Elliptic Dataset en Kaggle

## 👤 Autor
Sebastián Deghi
GitHub: @SebastianDeghi