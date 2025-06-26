
# Modelos de Aprendizaje Supervisado para Predecir Matrículas Estudiantiles en Ecuador

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
      - RMSE (Raíz del Error Cuadrático Medio) 
      - Error Relativo Promedio  (ERP)
    - Comparación de desempeño por provincia

11. **Predicción de Años Futuros**  
    Proyección de matrículas estudiantiles para años futuros utilizando el modelo con mejor desempeño (XGBoost).

12. **Interfaz Interactiva (ipywidgets)**  
    Widget para consultar predicciones por provincia y año.

13. **Visualización de Resultados**  
    Gráficos comparativos entre datos históricos y predicciones futuras.
    También se generó un mapa de calor para comparar el Error Relativo Promedio entre modelos por provincia.

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

Se evaluaron modelos supervisados usando validación rolling forecasting.
XGBoost Regressor obtuvo el mejor rendimiento según el Error Promedio Ponderado (EPP), calculado ponderando el error relativo por provincia con su respectivo índice de ruralidad. Esto prioriza la precisión en zonas con mayor población rural.

El modelo fue usado para proyectar matrículas futuras a nivel provincial. Las visualizaciones permiten identificar tendencias útiles para la planificación educativa.

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
