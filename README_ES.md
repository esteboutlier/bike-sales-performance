# Dashboard de Ventas de Bicicletas (Excel Project)

## 🌎 Idioma

> 📖 [Read in English](README.md) | [Leer en Español](README_ES.md)

## 📌 Descripción del Proyecto
Este proyecto consiste en un flujo completo de análisis de datos desarrollado íntegramente en **Microsoft Excel**. El objetivo principal es transformar un conjunto de datos "sucios" con información demográfica de clientes potenciales (`bike_buyers`) en un tablero de control interactivo (Dashboard) que responda a preguntas de negocio y facilite la toma de decisiones comerciales.

El análisis permite identificar qué factores (ingresos, distancia de viaje, edad o estado civil) influyen directamente en la decisión de un cliente de comprar o no una bicicleta.

---

## 🗺️ Fases del Proyecto

### 1. Limpieza y Preparación de Datos (Data Cleaning)
Para asegurar la calidad de los datos antes del análisis, se realizaron las siguientes acciones en una hoja de trabajo independiente (`Working Sheet`), preservando los datos originales:
* **Eliminación de Duplicados:** Detección y remoción de registros repetidos utilizando el identificador único (`ID`).
* **Normalización de Variables:** Transformación de abreviaturas a términos legibles mediante funciones de búsqueda y reemplazo (v.g., `M` $\rightarrow$ `Married`, `S` $\rightarrow$ `Single`, `F` $\rightarrow$ `Female`, `M` $\rightarrow$ `Male`).
* **Formateo:** Ajuste de columnas financieras (`Income`) a formato de moneda sin decimales redundantes para mejorar la lectura visual.

### 2. Ingeniería de Características (Feature Engineering)
* **Creación de Buckets de Edad:** Dado que las edades individuales generaban gráficos de líneas ruidosos y difíciles de interpretar, se implementó una función lógica `SI` anidada (`Nested IF`) para segmentar a los usuarios en tres categorías demográficas claras:
    * **Adolescents:** Menores de 31 años.
    * **Middle Age:** Entre 31 y 54 años.
    * **Old:** 55 años o más.

### 3. Procesamiento y Modelado de Datos
Utilizando **Tablas Dinámicas (Pivot Tables)**, se cruzaron las variables demográficas contra el KPI principal (`Purchased Bike`):
* **Análisis de Ingresos:** Cálculo del salario promedio agrupado por género y decisión de compra.
* **Análisis de Logística:** Conteo de clientes según la distancia de su viaje diario (`Commute Distance`).
* **Análisis Demográfico:** Agrupación de compras basada en los rangos de edad creados.

### 4. Visualización e Interactividad (Dashboard)
Diseño de una interfaz limpia eliminando las líneas de cuadrícula tradicionales de Excel y aplicando una paleta de colores corporativa uniforme:
* **Gráfico de Barras Agrupadas:** Muestra la relación entre el ingreso promedio y el género.
* **Gráfico de Líneas:** Expone la tendencia de compra según las distancias de viaje.
* **Gráfico de Tendencia Generacional:** Permite identificar fácilmente qué grupo demográfico es el cliente ideal.
* **Segmentadores de Datos (Slicers):** Conexión de filtros interactivos de *Estado Civil*, *Región* y *Educación* a todas las gráficas en simultáneo para permitir la exploración personalizada de los datos.

![Dashboard](bike-sales-dashboard.png)

---

## 📈 Insights Clave del Negocio
* **Poder Adquisitivo:** Los clientes que finalmente compran una bicicleta registran, en promedio, ingresos salariales más altos que aquellos que deciden no hacerlo.
* **Rango de Edad Crítico:** El segmento de "Middle Age" (31-54 años) representa el volumen más robusto de compradores, mientras que los jóvenes menores de 31 muestran el menor interés en la conversión.
* **Efecto del Estado Civil:** Los clientes casados registran ingresos promedio superiores (entre \$8,000 y \$10,000 adicionales) en comparación con los solteros dentro del conjunto de datos.

---

## 🛠️ Herramientas Utilizadas
* **Software:** Microsoft Excel
* **Funciones Principales:** `IF` anidados, Buscar y Reemplazar, Formatos de celda personalizados.
* **Componentes de BI:** Tablas Dinámicas, Gráficos Dinámicos y Conexiones de Reportes con Segmentadores (Slicers).

---

## 📂 Estructura del Repositorio
* `/data`: Contiene el dataset original de compradores de bicicletas.
* `Bike_Sales_Project.xlsx`: Archivo ejecutable de Excel con los datos limpios, tablas dinámicas y el Dashboard interactivo final.
* `README.md`: Explicación detallada del proyecto.
