# Challenge-Telecom-X
Challenge Telecom X de Alura Latam


# Análisis de Datos de Telecomunicaciones X (Google Colab)

Este proyecto contiene un análisis de datos sobre la evasión (churn) de clientes de una empresa de telecomunicaciones, utilizando Python y librerías comunes de ciencia de datos. El análisis incluye etapas de extracción, normalización, transformación y visualización de datos, optimizado para su ejecución en Google Colab.

## 🚀 Configuración en Google Colab

### Requisitos Previos

No necesitas instalar Python ni Jupyter Notebook, ya que Google Colab proporciona un entorno preconfigurado basado en Jupyter con Python.

### Dependencias

Las siguientes librerías de Python son necesarias para ejecutar el cuaderno. Puedes instalarlas directamente en una celda de Colab ejecutando los siguientes comandos:

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

import plotly.express as px

## 💻 Cómo Ejecutar el Proyecto en Colab

1.  **Cargar los archivos:**
    * **Opción 1 (Recomendada - Para archivos temporales):** Sube el archivo `TelecomX_Data.json` y `Telecom X data frame.ipynb` directamente a tu sesión de Colab. Puedes hacerlo arrastrando los archivos a la sección de archivos en el panel izquierdo de Colab o usando el icono de "Subir" (un icono de carpeta con una flecha hacia arriba). Asegúrate de que `TelecomX_Data.json` esté en la raíz del entorno de Colab (usualmente `/content/`) junto con el cuaderno.
    * **Opción 2 (Para archivos persistentes - Usando Google Drive):** Si prefieres que tus archivos persistan entre sesiones, puedes montar Google Drive. En una celda de código de Colab, ejecuta:
        ```python
        from google.colab import drive
        drive.mount('/content/drive')
        ```
        Luego, coloca `TelecomX_Data.json` y `Telecom X data frame.ipynb` en una carpeta de tu Google Drive y ajusta la ruta en el código para que apunte a esa ubicación (ej. `/content/drive/MyDrive/TuCarpeta/TelecomX_Data.json`).

2.  **Abre el cuaderno:** Si subiste `Telecom X data frame.ipynb`, Colab lo abrirá automáticamente o podrás seleccionarlo desde la interfaz.

3.  **Ejecuta las celdas:** Una vez abierto el cuaderno, puedes ejecutar las celdas una por una o todas a la vez desde el menú "Runtime" (Entorno de ejecución) -> "Run all" (Ejecutar todo).

## ⚠️ Posibles Problemas y Soluciones

* **Archivo `TelecomX_Data.json` no encontrado:**
    * **Problema:** El cuaderno no puede cargar los datos y arroja un error `FileNotFoundError`.
    * **Solución:** Verifica que `TelecomX_Data.json` esté en la ubicación correcta.
        * Si lo subiste directamente, asegúrate de que esté en `/content/`.
        * Si usas Google Drive, verifica que la ruta en `pd.read_json()` sea la correcta (ej., `/content/drive/MyDrive/TuCarpeta/TelecomX_Data.json`).

* **Columnas con valores no numéricos en 'Cargos_Totales':**
    * **Problema:** Si los `Cargos_Totales` contienen valores que no son numéricos (por ejemplo, espacios en blanco o cadenas de texto), la conversión a numérico puede fallar.
    * **Solución:** El cuaderno ya incluye un manejo para esto (`errors='coerce'`) que convierte los errores a `NaN` (Not a Number) y luego se eliminan esas filas. Si el problema persiste, revisa el archivo JSON original para identificar patrones de datos inconsistentes.

* **Problemas con las librerías:**
    * **Problema:** Aunque Colab viene con muchas librerías preinstaladas, es posible que una actualización o una versión específica cause problemas (`ModuleNotFoundError`).
    * **Solución:** Asegúrate de ejecutar la celda `!pip install ...` al inicio de tu cuaderno para instalar o actualizar las dependencias necesarias.
