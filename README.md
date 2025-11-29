# 🚀 Proyecto Final Big Data: E-Commerce Analytics Pipeline

**Asignatura:** Big Data  
**Estudiante:** [Tu Nombre Completo]  
**Opción del Proyecto:** B (Pipeline Analítico Batch con Spark + DuckDB)

---

## 📋 Descripción del Proyecto

Este proyecto implementa una arquitectura de datos moderna para analizar el comportamiento de usuarios en un e-commerce multicategoría. El objetivo es procesar millones de registros de interacciones (vistas, carritos, compras) para extraer valor de negocio mediante herramientas de Big Data.

El flujo de trabajo transforma datos crudos (CSV comprimidos) en un **Data Lake particionado** optimizado para consultas analíticas de alta velocidad.

## 🏗️ Arquitectura de la Solución

El pipeline sigue un diseño por capas (Medallion Architecture simplificada):

1.  **Capa de Ingesta (Bronze):** Lectura masiva de archivos `.csv.gz` utilizando **Apache Spark**.
2.  **Capa de Procesamiento (Silver):** Limpieza, tipado y particionamiento de datos por fecha (`event_date`) almacenados en formato **Parquet**.
3.  **Capa de Análisis (Gold):** Consultas OLAP de alto rendimiento utilizando **DuckDB** (lectura *Zero-Copy*).
4.  **Capa de Visualización:** Dashboard interactivo integrado en Jupyter Notebook usando `ipywidgets` y `matplotlib`.

## 📦 Estructura del Repositorio

```text
/
├── notebook_proyecto_final.ipynb   # Notebook principal con todo el código
├── requirements.txt                # Librerías necesarias
├── README.md                       # Este archivo
├── /csv_data.zip                   # ⚠️ DATOS CRUDOS (DESCOMPRIMIR)
├── /silver_lake/                   # (Generado por Spark) Data Lake particionado
└── /assets/                        # Imágenes o diagramas (opcional)
