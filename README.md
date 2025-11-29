Proyecto Final Big Data: E-Commerce Analytics Pipeline

**Asignatura:** Big Data  
**Estudiante:** Diego A. Henríquez Núñez
**Opción del Proyecto:** B (Pipeline Analítico Batch con Spark + DuckDB)

---

## Descripción del Proyecto

Este proyecto implementa una arquitectura de datos moderna para analizar el comportamiento de usuarios en un e-commerce multicategoría. El objetivo es procesar millones de registros de interacciones (vistas, carritos, compras) para extraer valor de negocio mediante herramientas de Big Data.

El flujo de trabajo transforma datos crudos (CSV comprimidos) en un **Data Lake particionado** optimizado para consultas analíticas de alta velocidad.

## Arquitectura de la Solución

El pipeline sigue un diseño por capas:

1.  **Capa de Ingesta (Bronze):** Lectura masiva de archivos `.csv.gz` utilizando **Apache Spark**.
2.  **Capa de Procesamiento (Silver):** Limpieza, tipado y particionamiento de datos por fecha (`event_date`) almacenados en formato **Parquet**.
3.  **Capa de Análisis (Gold):** Consultas OLAP de alto rendimiento utilizando **DuckDB** (lectura *Zero-Copy*).
4.  **Capa de Visualización:** Dashboard interactivo integrado en Jupyter Notebook usando `ipywidgets` y `matplotlib`.

#Requisitos e Instalación

Prerrequisitos
1. -Python 3.8+
2.  Java (JDK 8, 11 o 17/21): Necesario para ejecutar Apache Spark. Asegúrate de tener configurada la variable de entorno JAVA_HOME.

#Instalación de Librerías

Ejecuta el siguiente comando para instalar las dependencias:
pip install pyspark duckdb pandas matplotlib ipywidgets

#¿Cómo Ejecutar el proyecto?
Abre una terminal o Anaconda Prompt en la carpeta del proyecto.
Inicia Jupyter Lab o Jupyter Notebook:

-jupyter notebook

Abre el archivo notebook_proyecto_final.ipynb.

Ejecuta las celdas en orden secuencial.
1. Etapa 1: Spark procesará los archivos CSV y creará la carpeta silver_lake.
2. Etapa 2: DuckDB realizará los análisis sobre los archivos Parquet.
3. Etapa 3: Al final del notebook, se renderizará el Dashboard Interactivo.

#Créditos y Dataset
Dataset Original: eCommerce behavior data from multi category store (Kaggle)

## 📦 Estructura del Repositorio

Deberías tener esta estructura para ejecutar el proyecto. Principalmente tener los dataset en la carpeta csv_data, las demás carpetas se crearán al ejecutar el código
Por razones del tamaño del dataset, este repositorio solo cuenta con README.md y el .ipynb.

```text
/ (Raíz de la entrega)
├── README.md                  # Este archivo (Instrucciones)
└── Trabajo final              # ARCHIVO DEL PROYECTO 
    │
    ├── notebook_proyecto_final.ipynb   # Notebook principal con todo el código
    ├── csv_data/                       # Datos Crudos (Archivos .csv.gz originales)
    ├── bronze_lake/                    # Capa Bronze (Conversion directa a Parquet)
    └── silver_lake/                    # Capa Silver (Datos limpios y particionados)



