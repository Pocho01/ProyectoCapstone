# Modelos de Aprendizaje Supervisado para la Predicción de Matrículas Estudiantiles en Ecuador

## 📌 Resumen

Este proyecto tiene como objetivo desarrollar e implementar modelos de aprendizaje supervisado que permitan estimar con alta precisión el número total de estudiantes matriculados en el sistema educativo ecuatoriano, utilizando datos históricos oficiales.  

El flujo de trabajo incluye:

- Limpieza y preprocesamiento de datos.
- Análisis exploratorio de datos (EDA).
- Ingeniería de características, incluyendo variables rezagadas.
- Entrenamiento, evaluación y comparación de modelos de regresión supervisada.
- Predicción de matrículas a futuro (2025–2028) a nivel provincial.

Se utilizan métricas como RMSE y Error Relativo para evaluar el rendimiento predictivo de los modelos. El enfoque busca generar información útil para la planificación y toma de decisiones en el sector educativo.

El desarrollo se realiza en Python, empleando bibliotecas de ciencia de datos, aprendizaje automático y visualización como `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `XGBoost` y `TensorFlow`.

---

## ⚙️ Requisitos

Este notebook está diseñado para ejecutarse en **Google Colab**. Para ello, se requiere:

- Montar Google Drive para acceder al conjunto de datos.
- Asegurarse de tener acceso al archivo CSV `registro-administrativo-historico_2009-2024-inicio.csv`

### 📦 Bibliotecas utilizadas

Las siguientes bibliotecas deben estar disponibles (usualmente preinstaladas en Colab):

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `xgboost`
- `tensorflow`
- `ipywidgets`
- `statsmodels`
- `IPython`
- `pylab`

---

## 🚀 Uso

### Ejecución

1. Abre el notebook en Google Colab.
2. Monta tu Google Drive para acceder al conjunto de datos.
3. Ejecuta las celdas secuencialmente.

### Proceso general del notebook:

1. **Carga y limpieza de datos.**
2. **Análisis exploratorio (EDA)** con visualizaciones para identificar patrones por provincia, régimen, sostenimiento y tipo de educación.
3. **Preparación de datos para modelado**, incluyendo variables de rezago (lags) y segmentación por provincia.
4. **Entrenamiento y evaluación de modelos supervisados**, incluyendo:
   - XGBoost Regressor
   - Random Forest Regressor
   - Decision Tree Regressor
   - Red Neuronal (Perceptrón Multicapa con TensorFlow)
5. **Comparación de métricas por provincia** usando RMSE y Error Relativo.
6. **Visualización de resultados reales vs. predichos** para provincias seleccionadas.
7. **Generación de predicciones para 2025–2028** usando el modelo con mejor rendimiento (XGBoost).
8. **Exportación de predicciones a `predicciones.csv`.**
9. **Visualización interactiva** con `ipywidgets` para consultar predicciones por provincia y año.

---

## 🧾 Conjunto de Datos

Se utiliza el archivo:  
`registro-administrativo-historico_2009-2024-inicio.csv`  

Debe contener las siguientes columnas clave:

- `Anio_lectivo`
- `Cod_Provincia`
- `Total_Docentes`
- `Total_Estudiantes`
- `Tipo_Educacion`
- `Sostenimiento`
- `Area`
- `Regimen_Escolar`
- `Jurisdiccion`

Estos datos permiten segmentar las observaciones y generar predicciones específicas por provincia.

---

## 📈 Evaluación de Modelos

Se emplean las siguientes métricas para evaluar el rendimiento de cada modelo por provincia:

- **RMSE (Root Mean Squared Error):** Mide la magnitud promedio de los errores absolutos al cuadrado.
- **Error Relativo:** Mide el error como un porcentaje relativo al valor real promedio, útil para comparación normalizada.
- **R² (Coeficiente de Determinación):** Aplica a modelos como XGBoost para evaluar la proporción de varianza explicada por el modelo.

Se imprime una tabla resumen con las métricas por modelo y provincia, ordenadas por Error Relativo para facilitar la selección del modelo más eficiente.

---

## 🔮 Predicciones Futuras

Los modelos entrenados, especialmente XGBoost, se utilizan para generar predicciones de matrícula estudiantil para cada provincia durante los años 2025–2028. Las salidas incluyen:

- **Archivo CSV (`predicciones.csv`)** con los resultados por provincia y año.
- **Widget interactivo** para consultar predicciones específicas.
- **Gráficos históricos vs. predicción futura** para visualización comparativa.

---
