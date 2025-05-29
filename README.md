# 📊 Proyecto Capstone: Predicción del Número de Estudiantes en el Sistema Educativo Ecuatoriano

Este proyecto consiste en el desarrollo de un modelo de **aprendizaje supervisado** para predecir el número de estudiantes matriculados en el sistema educativo ecuatoriano durante los próximos cuatro años.

---

## 👥 Autores

- **José Antonio Cobeña Cedeño**  
- **Kelly Monserrate España Andrade**

**Universidad de las Américas**  
**Maestría en Inteligencia de Negocios y Ciencia de Datos**

---

## 🧠 Objetivo

Construir un modelo de predicción basado en datos históricos de matrículas escolares con el fin de asistir en la **planificación educativa**, **distribución de recursos** y **toma de decisiones estratégicas** por parte de las autoridades del sector.

## 🛠️ Tecnologías Utilizadas

- Python 3.10+
- Pandas
- NumPy
- Scikit-learn
- Matplotlib / Seaborn
- Jupyter Notebook


## 📊 Metodología

1. **Recolección de datos**: Se utilizaron registros históricos del Ministerio de Educación del Ecuador.
2. **Limpieza y preprocesamiento**: 
   - Eliminación de valores nulos.
   - Conversión de tipos de datos.
   - Ingeniería de variables temporales.
3. **Modelado**: 
   - División de datos en entrenamiento y prueba.
   - Entrenamiento de modelos de regresión (XGBoost).
   - Evaluación con métricas como MAE, RMSE y R².
4. **Predicción**:
   - Proyección de la cantidad de estudiantes para los próximos 4 años.

## Contenido del notebook
El notebook sigue los siguientes pasos:

1.  **Importación de Librerías**: Carga de todas las bibliotecas necesarias (pandas, numpy, matplotlib, seaborn, statsmodels, ipywidgets, sklearn, xgboost).
2.  **Carga de Datos**: Montaje de Google Drive para cargar el archivo CSV `registro-administrativo-historico_2009-2024-inicio.csv`.
3.  **Limpieza y Preprocesamiento de Datos**:
    *   Manejo de valores nulos en la columna 'Anio_lectivo'.
    *   Extracción del año de inicio y conversión a tipo entero.
    *   Conversión de columnas numéricas de float a int donde sea posible.
    *   Estandarización de columnas de texto (eliminar espacios, convertir a minúsculas, normalizar caracteres).
    *   Codificación One-Hot (dummies) para variables categóricas.
4.  **Selección de Columnas y Preparación para Modelado**: Creación de un DataFrame con las columnas relevantes para el análisis y modelado.
5.  **Análisis Exploratorio de Datos (EDA)**:
    *   Configuración del índice a la columna 'Anio' (tipo datetime).
    *   Visualización de las tendencias anuales de 'Total_Docentes' y 'Total_Estudiantes'.
    *   Cálculo y visualización de la matriz de correlación entre 'Total_Docentes' y 'Total_Estudiantes'.
    *   Visualización del total de estudiantes por diferentes variables categóricas.
6.  **Agregación y Creación de Features**:
    *   Agrupación de datos por provincia y año para sumar totales y calcular promedios de variables codificadas.
    *   Creación de variables de retraso (lags) para 'Total_Estudiantes' (hasta 3 años atrás).
    *   Eliminación de filas con valores nulos resultantes de los lags.
7.  **División de Datos**: Separación del conjunto de datos en entrenamiento (hasta 2021) y prueba (después de 2021).
8.  **Entrenamiento y Evaluación del Modelo XGBoost**:
    *   Inicialización y entrenamiento del modelo `XGBRegressor`.
    *   Realización de predicciones en el conjunto de prueba.
    *   Cálculo y presentación de métricas de evaluación (RMSE y R²).
    *   Visualización y tabla de la importancia de las características en el modelo.
9.  **Comparación de Resultados**: Gráfica comparativa de los totales reales y predichos de estudiantes a lo largo del tiempo.
10. **Análisis de Rendimiento por Provincia**: Cálculo y ordenamiento del RMSE del modelo para cada provincia.
11. **Predicción de Valores Futuros**:
    *   Implementación de una función para predecir el total de estudiantes por provincia para años futuros, utilizando los lags.
    *   Generación de predicciones para los próximos 4 años (a partir de 2025).
    *   Exportación de las predicciones a un archivo CSV (`predicciones_matriculados.csv`).
    *   Descarga automática del archivo CSV generado.
12. **Interfaz de Consulta**: Creación de widgets interactivos para ingresar el código de provincia y el año, y mostrar la predicción específica.


## 📈 Resultados Esperados

- Predicciones anuales del total de estudiantes.
- Visualizaciones de tendencias educativas.

## ✅ Requisitos

- Python >= 3.10
- Jupyter
- Paquetes: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

Puedes instalar los requerimientos con:

```bash
pip install -r requirements.txt


