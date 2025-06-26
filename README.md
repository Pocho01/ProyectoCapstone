
# Modelos de Aprendizaje Supervisado para el Número de Matrículas Estudiantiles en Ecuador

Este proyecto implementa modelos de aprendizaje supervisado para predecir el número total de estudiantes matriculados en Ecuador a nivel provincial, utilizando datos históricos. El objetivo es identificar el modelo con el mejor rendimiento predictivo para apoyar la planificación educativa.

---

## 📘 Contenido del Notebook

El archivo principal `ProyectoCapstone.ipynb` sigue los siguientes pasos:

1. **Importación de Librerías**  
   Carga de bibliotecas para manipulación de datos, visualización, análisis estadístico y modelado predictivo.

2. **Carga de Datos**  
   Lectura del dataset histórico desde Google Drive (`registro-administrativo-historico_2009-2024-inicio.csv`).

3. **Exploración Inicial de Datos**  
   Visualización de estructura y tipos de datos para entender el dataset.

4. **Limpieza y Preprocesamiento**  
   - Conversión de tipos de datos  
   - Estandarización de texto  
   - One-Hot Encoding  
   - Filtrado de registros incompletos  
   - Selección de variables relevantes

5. **Preparación para Series de Tiempo**  
   - Conversión de año a índice datetime  
   - Agregación por año

6. **Análisis Exploratorio de Datos (EDA)**  
   - Tendencias temporales  
   - Matriz de correlación  
   - Análisis por categoría (área, sostenimiento, tipo de educación, etc.)

7. **Agregación Provincial Anual**  
   Agrupación por provincia y año, sumando totales y promediando variables categóricas.

8. **Ingeniería de Características (Lags)**  
   Generación de variables de retraso (`lags`) para capturar dependencia temporal.

9. **Validación Rolling Forecasting**  
   Estrategia de validación temporal simulando escenarios reales de predicción año a año.

10. **Entrenamiento y Evaluación de Modelos**  
    - Modelos utilizados:
      - XGBoost Regressor  
      - Gradient Boosting Regressor  
      - Random Forest Regressor  
      - Decision Tree Regressor  
    - Métricas evaluadas:
      - RMSE  
      - Error Relativo Promedio  
    - Comparación de desempeño por provincia

11. **Predicción de Años Futuros (XGBoost)**  
    Predicción de matrículas para años futuros usando el mejor modelo entrenado.

12. **Interfaz Interactiva (ipywidgets)**  
    Widget para consultar predicciones por provincia y año.

13. **Visualización de Resultados**  
    Gráficos comparativos entre datos históricos y predicciones futuras.
    Además, se generó un heatmap para visualizar comparativamente el Error Relativo Promedio de cada modelo por provincia.

---

## ⚙️ Requisitos

- Cuenta de Google y acceso a Google Colab  
- Archivo de datos en Google Drive:  
  `/content/drive/My Drive/Colab Notebooks/registro-administrativo-historico_2009-2024-inicio.csv`  
- Librerías de Python necesarias:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels xgboost ipywidgets
```

O usa este `requirements.txt`:

```text
pandas==2.0.3
numpy==1.25.2
matplotlib==3.7.1
seaborn==0.13.1
statsmodels==0.14.0
ipywidgets==7.7.1
scikit-learn==1.5.0
xgboost==2.0.0
ipython==9.3.0
```

---

## ▶️ Cómo Ejecutar

1. Abre el notebook en Google Colab.  
2. Monta tu Google Drive:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

3. Asegúrate de que el archivo CSV esté en la ruta especificada o ajústala en el código.  
4. Ejecuta cada celda del notebook en orden.  
5. Utiliza el widget interactivo para consultar predicciones por provincia y año.

---

## 📈 Resultados y Conclusiones

El notebook evalúa múltiples modelos de regresión para predecir matrículas estudiantiles a nivel provincial.  
El notebook evalúa múltiples modelos de regresión para predecir matrículas estudiantiles a nivel provincial.  
El modelo **XGBoost Regressor** mostró el mejor desempeño promedio, con el menor **Error Promedio Ponderado (EPP)**, y se utilizó para realizar predicciones futuras.  
Los resultados permiten visualizar tendencias proyectadas que pueden ser útiles en planificación educativa nacional y regional.

---

## 📁 Estructura del Proyecto

```
.
├── ProyectoCapstone.ipynb         # Notebook principal
└── predicciones_xgboost_futuras.csv  # Archivo de salida con predicciones
```
---

## 👤 Autores

José Cobeña y Kelly España
