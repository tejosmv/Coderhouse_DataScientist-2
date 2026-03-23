# Coderhouse_DataScientist-2 🚀
Desarrollo del proyecto de análisis propuesto del curso, con el fin de entregar las consignas.

---

## Radiografía del Mercado de Arriendos en la Región Metropolitana (Chile) 🏢📊

Este repositorio contiene el Análisis Exploratorio de Datos (EDA) y las visualizaciones correspondientes a la **Primera Entrega** del proyecto de Data Science. 

El objetivo principal de este proyecto es decodificar los factores clave (ubicación, metraje, amenidades) que determinan el precio final de los arriendos en la Región Metropolitana, permitiendo detectar tendencias de mercado, sobreprecios y oportunidades tanto para inversionistas como para futuros arrendatarios.

### 📂 Estructura del Repositorio

El proyecto está organizado de la siguiente manera para facilitar su revisión y reproducción:

* 📝 **`Analitical.ipynb`**: Jupyter Notebook principal. Contiene todo el código en Python detallando el proceso de importación (simulación de API), limpieza de datos (*Data Wrangling*), manejo de *outliers* y la generación del Análisis Exploratorio (EDA).
* 📊 **`Primera_Entrega_vtejos.pdf`**: Presentación ejecutiva orientada a negocio. Resume el contexto, la metadata, las hipótesis planteadas y los *insights* finales sin saturar con código técnico.
* 💾 **`clean_alquiler_02_11_2023cc.csv`**: Dataset crudo utilizado para el análisis (extraído originalmente vía *web scraping* de portales inmobiliarios).
* 🖼️ **`viz_1_ubicacion.png` / `viz_2_superficie.png` / `viz_3_costos_ocultos.png`**: Visualizaciones ejecutivas generadas automáticamente desde el notebook y utilizadas en la presentación final.

### 🔎 Preguntas e Hipótesis de Negocio

El análisis se estructuró para responder tres preguntas fundamentales del mercado inmobiliario:
1.  **Ubicación:** ¿Cómo varía el precio promedio según la comuna y dónde están las zonas más exclusivas?
2.  **Espacio y "Premium":** ¿Es lineal la relación entre metros cuadrados y precio, o existen factores (como tener estacionamiento) que alteran drásticamente el valor?
3.  **Costos Ocultos:** ¿Qué carga financiera real representan los gastos comunes, especialmente en departamentos de menor tamaño?

### 🚀 Principales Insights Obtenidos

* **Polarización Geográfica:** El sector oriente (ej. Vitacura, Las Condes) domina el mercado, duplicando el valor promedio de comunas residenciales clásicas.
* **El Efecto Estacionamiento:** Tener un estacionamiento no es solo un "extra" proporcional al tamaño, sino que genera un salto estructural en el valor base del arriendo, independientemente de los metros cuadrados.
* **Regresividad de los Gastos Comunes:** En propiedades de 1 dormitorio, los gastos comunes actúan como un costo fijo regresivo, añadiendo hasta un 15%-20% extra sobre el valor del arriendo base y afectando fuertemente el presupuesto total.

### 🛠️ Tecnologías y Librerías Utilizadas

* **Lenguaje:** Python 3
* **Manipulación de Datos:** `pandas`, `numpy`
* **Visualización:** `matplotlib`, `seaborn`
* **Entorno:** Jupyter Notebook / Google Colab

### 🔗 Fuente de Datos

Los datos crudos utilizados en este análisis provienen del mercado inmobiliario chileno (Noviembre 2023) y se encuentran disponibles públicamente a través de Kaggle:
* [Propiedades Alquiler PortalInmobiliario - Kaggle Dataset](https://www.kaggle.com/datasets/edwight/propiedades-alquiler-portalinmobiliario)

---
**Autor:** Vicente Tejos Medel (tejosmv)
