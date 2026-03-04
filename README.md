
# 📊 Predicción de Churn en Telecomunicaciones (TelecomX)

![Data Science](https://img.shields.io/badge/Python-3.12-blue.svg)
![Status](https://img.shields.io/badge/Status-Completado-green.svg)

## 📝 Descripción del Proyecto
Este repositorio contiene un análisis de punta a punta para predecir la **cancelación de clientes** (Churn) en una empresa de telecomunicaciones. El objetivo es proporcionar al departamento de marketing una herramienta que identifique clientes en riesgo para aplicar estrategias de retención proactivas.


---
## 📁 Estructura del Proyecto
El repositorio está organizado de la siguiente manera:
* **`TelecomX_Analysis.ipynb`**: Cuaderno principal con todo el flujo de trabajo (Limpieza, EDA, Modelado).
* **`data/`**: Carpeta que contiene el dataset original en JSON y los datos procesados en formato CSV.
* **`visualizaciones/`**: Carpeta con los gráficos exportados (Matrices de confusión, Importancia de variables, Boxplots).
* **`README.md`**: Descripción detallada del proyecto.
---
## ⚙️ Preparación de los Datos
El proceso de ingeniería de datos se dividió en etapas críticas:

### 1. Clasificación de Variables
* **Numéricas:** `Meses_Permanencia` (tenure), `Monto_Mensual`, `Monto_Total`.
* **Categóricas:** `Genero`, `Tipo_Contrato`, `Socio`, `Dependientes`, entre otras.

### 2. Normalización y Codificación
* **Codificación:** Se aplicó `pd.get_dummies` para transformar variables categóricas en numéricas (One-Hot Encoding).
* **Normalización:** Se utilizó `StandardScaler` para los modelos de Regresión Logística, asegurando que variables con rangos grandes (como Monto Total) no sesguen el modelo.
* **Balanceo:** Se utilizó la técnica **SMOTE** para equilibrar las clases, ya que el número de clientes que no cancelan era superior a los que sí.

### 3. Separación de Datos
Se realizó una división de **70% Entrenamiento** y **30% Prueba** utilizando `train_test_split` con una semilla aleatoria (`random_state=42`) para garantizar la reproducibilidad de los resultados.

---

## 📈 Análisis Exploratorio (EDA) - Insights
Durante el análisis, se obtuvieron los siguientes hallazgos visuales:

* **Contratos vs Cancelación:** Los gráficos de barras revelaron que los clientes con contrato **Mes a Mes** tienen la tasa de deserción más alta.
* **Impacto de la Permanencia:** Los Boxplots mostraron que el riesgo de fuga se concentra en los clientes con **menos de 12 meses** de antigüedad.
* **Gasto Mensual:** Se observó que los clientes que cancelan suelen tener cargos mensuales promedio más altos que los que permanecen.

---

## 🤖 Modelización y Justificación
Se entrenaron dos modelos con enfoques distintos:
1. **Regresión Logística:** Elegido por su facilidad de interpretación y su excelente **Recall (98.6%)**, ideal para no dejar escapar a ningún cliente potencial en riesgo.
2. **Random Forest:** Elegido por su capacidad para manejar relaciones no lineales y proporcionar una **importancia de variables** robusta basada en la reducción de impureza de Gini.

---

## 🚀 Instrucciones de Ejecución

### 1. Instalación de Bibliotecas
Asegúrate de tener instalado Python 3.12 y ejecuta el siguiente comando para instalar las dependencias necesarias:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
  
### 2. Carga de Datos
Para cargar los datos procesados dentro del cuaderno, utiliza el siguiente bloque de código:

```python
import pandas as pd

# Carga del dataset procesado
df = pd.read_csv('data/telecom_processed.csv')



3. Ejecución
Sigue estos pasos para reproducir el análisis:

Abre el archivo TelecomX_Analysis.ipynb en VS Code o Google Colab.

Asegúrate de que la ruta del dataset en el código coincida con la ubicación de tu archivo .csv o .json.

Ejecuta las celdas secuencialmente para observar el preprocesamiento, los resultados del entrenamiento y las métricas de evaluación final.
