# Coderhouse_DataScientist-2 🚀

Proyecto final desarrollado para el curso **Data Scientist II - Coderhouse**, enfocado en el análisis exploratorio y modelamiento predictivo del mercado de arriendos en la Región Metropolitana de Chile.

---

## Radiografía del Mercado de Arriendos en la Región Metropolitana (Chile) 🏢📊

Este proyecto analiza el mercado de arriendos en la Región Metropolitana con el objetivo de identificar los principales factores que influyen en el precio mensual de una propiedad.

El trabajo comenzó con un **Análisis Exploratorio de Datos (EDA)**, donde se estudiaron variables como ubicación, superficie, estacionamiento, gastos comunes y características generales de los inmuebles. Posteriormente, se desarrolló una etapa de **Machine Learning**, orientada a entrenar y optimizar modelos capaces de predecir el precio mensual de arriendo.

El objetivo final es construir una herramienta analítica que permita estimar precios de arriendo y apoyar la toma de decisiones de inversionistas, arrendatarios y analistas del mercado inmobiliario.

---

## Objetivo General 🎯

Desarrollar un modelo predictivo que permita estimar el precio mensual de arriendo de propiedades ubicadas en la Región Metropolitana, utilizando variables inmobiliarias, geográficas y económicas relevantes.

---

## Objetivos Específicos

- Realizar un análisis exploratorio de datos del mercado de arriendos.
- Identificar patrones asociados a ubicación, superficie, estacionamiento, bodegas y gastos comunes.
- Preparar y limpiar el dataset para su uso en modelos de Machine Learning.
- Tratar valores nulos, outliers y superficies anómalas.
- Crear nuevas variables mediante ingeniería de atributos.
- Entrenar distintos modelos de regresión supervisada.
- Optimizar hiperparámetros mediante `RandomizedSearchCV`.
- Evaluar modelos mediante MAE, RMSE y R².
- Implementar un modelo ensemble mediante `VotingRegressor`.
- Seleccionar el modelo con mejor desempeño predictivo.

---

## Problema de Machine Learning 🤖

El proyecto se aborda como un problema de **regresión supervisada**, donde la variable objetivo corresponde al precio mensual de arriendo de una propiedad.

### Variable objetivo

- `precio`

### Variables predictoras utilizadas

- `superficie_total`
- `superficie_util`
- `superficie_terraza`
- `dormitorios`
- `banos`
- `estacionamientos`
- `bodegas`
- `gastos_comunes`
- `latitude`
- `longitude`
- `comuna`
- `zona_comuna`
- Variables derivadas mediante ingeniería de atributos

---

## Estructura del Repositorio 📂

El repositorio contiene los siguientes archivos principales:

| Archivo | Descripción |
|---|---|
| `Analitical.ipynb` | Notebook principal del proyecto. Contiene EDA, limpieza de datos, ingeniería de atributos, entrenamiento, optimización y evaluación de modelos de Machine Learning. |
| `clean_alquiler_02_11_2023cc.csv` | Dataset utilizado para el análisis y modelamiento predictivo del mercado de arriendos. |
| `modelo_prediccion_arriendos_rm.pkl` | Modelo final exportado mediante `joblib` para reutilización posterior. |
| `Primera_Entrega_vtejos.pdf` | Presentación ejecutiva de la primera entrega, enfocada en el análisis exploratorio de datos. |
| `Primera_Entrega_vtejos.pptx` | Versión editable de la presentación de la primera entrega. |
| `Tejos_Vicente_DS2_ProyectoFinal_ArriendosRM_ML.pdf` | Presentación final del proyecto, enfocada en resultados de Machine Learning. |
| `viz_1_ubicacion.png` | Visualización asociada al análisis por ubicación/comuna. |
| `viz_2_superficie.png` | Visualización asociada a superficie y precio. |
| `viz_3_costos_ocultos.png` | Visualización asociada a gastos comunes y costos adicionales. |

> Nota: El archivo `csic_database.csv`, si no forma parte del proyecto de arriendos, debería eliminarse del repositorio o moverse fuera de la entrega para evitar confusión.

---

## Preguntas de Negocio 🔎

El análisis se estructuró inicialmente para responder las siguientes preguntas:

1. **Ubicación:**  
   ¿Cómo varía el precio promedio según la comuna?

2. **Superficie y características premium:**  
   ¿La relación entre metros cuadrados y precio es lineal o existen variables adicionales que alteran el valor?

3. **Costos ocultos:**  
   ¿Qué carga financiera representan los gastos comunes en el costo total del arriendo?

4. **Predicción:**  
   ¿Es posible estimar el precio mensual de arriendo de una propiedad utilizando sus características físicas, ubicación y costos asociados?

---

## Ingeniería de Atributos ⚙️

Para mejorar la capacidad predictiva de los modelos, se crearon nuevas variables a partir de los datos originales:

- `tiene_estacionamiento`
- `tiene_bodega`
- `terraza_ratio`
- `gasto_comun_por_m2`
- `densidad_dormitorios`
- `densidad_banos`
- `zona_comuna`

Estas variables permiten representar mejor elementos relevantes del mercado inmobiliario, como la disponibilidad de estacionamiento, presencia de bodega, proporción de terraza, intensidad de uso del espacio y ubicación geográfica.

---

## Modelos Entrenados 🧠

Se entrenaron y compararon distintos modelos de regresión:

| Modelo | Descripción |
|---|---|
| Ridge Regression | Modelo lineal regularizado utilizado como línea base. |
| Random Forest Regressor | Modelo basado en árboles capaz de capturar relaciones no lineales. |
| Gradient Boosting Regressor | Modelo secuencial orientado a mejorar errores de predicción. |
| Voting Regressor | Modelo ensemble que combina predicciones de distintos algoritmos. |

Además, se aplicaron técnicas de:

- Separación Train/Test.
- Validación cruzada con `KFold`.
- Optimización de hiperparámetros con `RandomizedSearchCV`.
- Evaluación mediante MAE, RMSE y R².
- Análisis de importancia de variables por permutación.

---

## Resultados Principales 📊

La comparación final de modelos entregó los siguientes resultados:

| Modelo | MAE | RMSE | R² |
|---|---:|---:|---:|
| Random Forest Optimizado | $45.712 | $90.493 | 0.9023 |
| Gradient Boosting Optimizado | $47.722 | $88.681 | 0.9062 |
| Voting Regressor Ensemble | $47.902 | $83.909 | 0.9160 |
| Random Forest | $48.810 | $87.522 | 0.9086 |
| Gradient Boosting | $48.849 | $83.083 | 0.9176 |
| Ridge Regression | $52.016 | $88.446 | 0.9067 |

El modelo seleccionado fue **Random Forest Optimizado**, ya que obtuvo el menor MAE, es decir, el menor error promedio en pesos chilenos.

Si bien otros modelos presentaron mejores valores de R² o RMSE, se priorizó MAE debido a que es la métrica más interpretable para el contexto del negocio inmobiliario.

---

## Principales Insights 🚀

- **La ubicación es un factor determinante:**  
  La comuna y la zona geográfica tienen alta influencia en el precio mensual de arriendo.

- **La superficie no explica todo el precio:**  
  El valor de arriendo también depende de variables como baños, dormitorios, estacionamientos, bodegas y gastos comunes.

- **Los gastos comunes representan un costo relevante:**  
  En algunos casos, los gastos comunes aumentan significativamente el costo mensual real de una propiedad.

- **Los modelos no lineales tuvieron mejor desempeño:**  
  Random Forest y Gradient Boosting superaron al modelo lineal base, lo que indica que la relación entre las variables inmobiliarias y el precio no es estrictamente lineal.

- **El modelo funciona como herramienta de apoyo:**  
  El modelo no reemplaza una tasación formal, pero permite estimar valores de mercado y detectar posibles propiedades sobrevaloradas o subvaloradas.

---

## Tecnologías y Librerías Utilizadas 🛠️

- **Lenguaje:** Python 3
- **Entorno:** Jupyter Notebook / Google Colab
- **Manipulación de datos:** `pandas`, `numpy`
- **Visualización:** `matplotlib`, `seaborn`
- **Machine Learning:** `scikit-learn`
- **Modelos:** `Ridge`, `RandomForestRegressor`, `GradientBoostingRegressor`, `VotingRegressor`
- **Optimización:** `RandomizedSearchCV`
- **Exportación de modelo:** `joblib`

---

## Fuente de Datos 🔗

Los datos utilizados corresponden al mercado inmobiliario chileno y se encuentran disponibles públicamente a través de Kaggle:

- [Propiedades Alquiler PortalInmobiliario - Kaggle Dataset](https://www.kaggle.com/datasets/edwight/propiedades-alquiler-portalinmobiliario)

---

## Limitaciones del Modelo ⚠️

El modelo debe interpretarse como una herramienta de apoyo y no como una tasación inmobiliaria definitiva.

Algunas limitaciones identificadas son:

- El dataset puede contener errores de carga o formato en variables como superficie.
- Algunas propiedades de alto valor o con características atípicas pueden presentar errores mayores.
- No se incorporaron variables externas como cercanía al metro, antigüedad del edificio, seguridad del sector, conectividad o equipamiento urbano.
- El análisis depende de la calidad y disponibilidad de los datos originales.

---

## Próximas Mejoras 🔮

Como trabajo futuro, se podrían incorporar:

- Distancia a estaciones de metro.
- Cercanía a colegios, supermercados, hospitales y áreas verdes.
- Antigüedad del edificio.
- Índices de seguridad o calidad de vida por comuna.
- Mayor cantidad de datos actualizados.
- Dashboard interactivo para consulta de precios estimados.
- Despliegue del modelo en una aplicación web simple.

---

## Autor 👤

**Vicente Tejos Medel**  
Proyecto desarrollado como parte del curso **Data Scientist II - Coderhouse**.

---
