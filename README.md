
# 📊 Predicción de Churn en Telecomunicaciones (TelecomX)

![Data Science](https://img.shields.io/badge/Python-3.12-blue.svg)
![Status](https://img.shields.io/badge/Status-Completado-green.svg)

## 📝 Descripción del Proyecto
Este repositorio contiene un análisis de punta a punta para predecir la **cancelación de clientes** (Churn) en una empresa de telecomunicaciones. El objetivo es proporcionar al departamento de marketing una herramienta que identifique clientes en riesgo para aplicar estrategias de retención proactivas.


---

## 🛠️ Tecnologías y Herramientas
* **Análisis de Datos:** `Pandas`, `NumPy`
* **Visualización:** `Matplotlib`, `Seaborn`
* **Machine Learning:** `Scikit-Learn` (Regresión Logística, Random Forest)
* **Balanceo de Datos:** `SMOTE` 

---
## 📈 Proceso de Análisis
1. Exploración y Preparación 
Identificamos que las variables con mayor impacto en la decisión del cliente son el Tipo de Contrato, los Meses de Permanencia y el Monto Mensual. Se realizó un preprocesamiento de datos que incluyó:

* Conversión de tipos de datos numéricos.

* Tratamiento de valores nulos y duplicados.

* Estandarización de variables para modelos sensibles a la escala.

2. Modelado y Evaluación
Se entrenaron y compararon dos arquitecturas para maximizar la detección de clientes en riesgo:
* Regresión Logística: (Con normalización) para capturar tendencias lineales.
* Random Forest: (Modelo de ensamble) para capturar comportamientos no lineales complejos.

---

## 📈 Hallazgos Principales (EDA)
Durante el Análisis Exploratorio de Datos, se determinaron los siguientes puntos clave:
1. **Contratos:** Los clientes con contrato **mes a mes** representan el mayor volumen de fugas.
2. **Permanencia:** El riesgo de cancelación disminuye drásticamente después de los **12 meses** de antigüedad.
3. **Cargos:** El monto mensual facturado tiene un impacto directo en la decisión de abandono.

---

## 🤖 Modelado y Resultados
Se compararon dos modelos, siendo la **Regresión Logística** la más eficiente para los objetivos de negocio (priorizando la detección sobre la precisión absoluta).

| Métrica | Regresión Logística | Random Forest |
| :--- | :---: | :---: |
| **Exactitud** | 85.3% | 86.6% |
| **Recall (Detección)** | **98.6%** | 86.8% |
| **F1-Score** | **0.87** | 0.86 |


---

## 💡 Estrategias de Retención Recomendadas
* **Incentivos de Contrato:** Bonos especiales para clientes que migren de planes mensuales a anuales.
* **Optimización de Planes:** Ofrecer proactivamente ajustes de tarifa a clientes con cargos mensuales elevados que presenten patrones de uso decreciente.

* Priorizar la atención al cliente durante los primeros 6 meses, detectados como el periodo de mayor vulnerabilidad.
