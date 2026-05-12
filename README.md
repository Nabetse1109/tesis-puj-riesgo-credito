# Gestión del Riesgo y Cobranza mediante Modelos Predictivos en Ciencia de Datos

**Proyecto de grado — Maestría en Ciencia de Datos**  
Pontificia Universidad Javeriana Cali — Facultad de Ingeniería y Ciencias

---

## 📌 Descripción

Este repositorio contiene el desarrollo técnico completo del proyecto aplicado de maestría titulado *"Gestión del Riesgo y Cobranza mediante Modelos Predictivos en Ciencia de Datos en Educación Superior"*, realizado sobre los datos del Departamento de Apoyo Financiero de la Universidad Autónoma de Occidente (UAO).

El proyecto implementa la metodología **CRISP-DM** para construir un modelo predictivo que anticipe el incumplimiento en créditos educativos institucionales y facilite la priorización de cobranza preventiva.

## 🎯 Objetivo general

Desarrollar un modelo predictivo basado en técnicas de ciencia de datos que permita identificar tempranamente el riesgo de incumplimiento en créditos educativos otorgados por instituciones de educación superior, facilitando la toma de decisiones estratégicas en la gestión del riesgo crediticio.

## 🧩 Objetivos específicos

1. Analizar las variables académicas, socioeconómicas y de comportamiento asociadas al riesgo de incumplimiento.
2. Preparar, transformar y depurar los datos históricos del sistema de financiación institucional.
3. Implementar y evaluar modelos de clasificación para anticipar el riesgo de incumplimiento.
4. Aplicar técnicas de segmentación y diseñar un tablero de control interactivo.

## 📊 Resultados principales

| Métrica | Valor |
|---|---|
| Modelo interpretable | Regresión Logística (AUC = 0,846) |
| Modelo operativo | Random Forest (AUC = 0,856) |
| Recall de la clase morosa | 85% |
| Cobertura interviniendo al 10% superior | 67,8% de los morosos capturados |
| ROI de la estrategia de cobranza | +1.079% |
| Créditos 2025 scoreados | 14.938 (clasificados ALTO / MEDIO / BAJO) |

## 🗺️ Metodología CRISP-DM aplicada

1. **Comprensión del negocio** — diagnóstico del proceso de crédito UAO.
2. **Comprensión de los datos** — auditoría de 191.130 registros, validación cruzada df1 × df2.
3. **Preparación de datos** — protocolo anti-leakage (7 variables excluidas), 14 features prospectivas con esquema t→t+1, ventana cerrada con 90 días de gracia, exclusión de vintages 2025.
4. **Modelado** — Regresión Logística, Árbol de Decisión, Random Forest, Gradient Boosting con SMOTE dentro de pipelines de CV.
5. **Evaluación** — split temporal (corte 2022), CV 5-fold estratificada, validación out-of-time, SHAP, PSI, calibración.
6. **Despliegue** — zonas semáforo, deciles, simulación de impacto, costo-beneficio, dashboard Plotly, scoring de la población 2025.

## 📁 Estructura del repositorio

```
.
├── README.md                                          # Este archivo
├── requirements.txt                                   # Dependencias Python
├── .gitignore                                         # Archivos ignorados
│
├── notebook/
│   └── UAO_Riesgo_Crediticio.ipynb                    # Notebook completo ejecutado
│
├── outputs/
│   ├── scoring_2025_para_cobranza.csv                 # Scoring de los 14.938 créditos 2025
│   ├── predicciones_UAO_riesgo_crediticio.csv         # Predicciones del holdout 2023-2024
│   ├── perfiles_clusters_UAO.csv                      # Perfiles de los 2 clusters
│   ├── zonas_riesgo_UAO.csv                           # Distribución por zonas semáforo
│   ├── entregables_UAO_riesgo.xlsx                    # Excel consolidado (8 hojas)
│   └── tablero_control_UAO_riesgo_crediticio.html     # Dashboard interactivo Plotly
│
└── data/
    └── README_DATOS.md                                # Nota sobre confidencialidad
```

## ▶️ Cómo abrir el notebook

### Opción 1 — Ver directamente en GitHub (recomendado)
Haz clic en [`notebook/UAO_Riesgo_Crediticio.ipynb`](notebook/UAO_Riesgo_Crediticio.ipynb) y GitHub lo renderiza con código, tablas y los 33 gráficos embebidos.

### Opción 2 — Visualización alternativa con nbviewer
Si GitHub tarda en cargar (el notebook pesa ~8 MB con todos los gráficos embebidos):

```
https://nbviewer.org/github/Nabetse1109/tesis-puj-riesgo-credito/blob/main/notebook/UAO_Riesgo_Crediticio.ipynb
```

### Opción 3 — Ejecutarlo localmente
```bash
git clone https://github.com/Nabetse1109/tesis-puj-riesgo-credito.git
cd tesis-puj-riesgo-credito
pip install -r requirements.txt
jupyter notebook notebook/UAO_Riesgo_Crediticio.ipynb
```

## 🧪 Requisitos técnicos

- Python 3.10+
- Las librerías listadas en `requirements.txt`
- Semilla global `SEMILLA = 42` y fecha de corte fija `FECHA_ANALISIS = 2026-03-15` para reproducibilidad determinista.

## 👥 Autores

- **Edgar Esteban Grajales Castaño** — eegrajales@javerianacali.edu.co
- **Paula Andrea Tovar Ríos** — paolat87@javerianacali.edu.co

**Directora:** Dra. Isabel Cristina García Arboleda

## 🔒 Confidencialidad de los datos

Los datos utilizados son **internos del Departamento de Apoyo Financiero de la Universidad Autónoma de Occidente** y se emplearon exclusivamente con fines académicos en el marco de la Maestría en Ciencia de Datos de la Pontificia Universidad Javeriana Cali.

**Por motivos de confidencialidad institucional, los archivos de datos originales (`1_Creditos_EstudiantesREV.xlsx` y `2_Cartera_depuradaREV.xlsx`) NO están incluidos en este repositorio.** El notebook se entrega en su forma ejecutada — con todos los outputs visibles — pero no es reproducible sin acceso a las fuentes originales.

El tratamiento de los datos personales se rige por la **Ley 1581 de 2012 (Protección de Datos Personales en Colombia)** y la política institucional de la UAO. Ningún identificador personal (nombres, documentos, contactos) se incluye en los outputs publicados.

Las columnas `Cliente` y `Nota_debito` que aparecen en los CSVs de outputs son códigos numéricos internos sin información personal directa.

## 📅 Fecha de cierre del análisis

**15 de diciembre de 2025** (fecha de corte fija configurada en el notebook para garantizar reproducibilidad determinista).

---

*Este repositorio acompaña el documento de tesis entregado a la Pontificia Universidad Javeriana Cali como requisito parcial para optar al título de Magíster en Ciencia de Datos.*
