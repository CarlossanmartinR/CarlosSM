# 🧠 Predict Podcast Listening Time – Machine Learning con Jupyter

Este proyecto aborda el desafío de predecir el tiempo de escucha de episodios de podcast, utilizando técnicas de aprendizaje automático.  
El trabajo se realizó en **Jupyter Notebook** e incluye análisis de datos, preprocesamiento, tuning de modelos y generación de predicciones para envío.

---

## 📂 Contenido del notebook

- **Carga de datos desde Kaggle API**  
  (El notebook está diseñado para funcionar localmente, leyendo el archivo `kaggle.json`.)

- **Exploración y limpieza de datos**
  - Análisis de valores nulos
  - Transformación de variables categóricas
  - Detección de outliers y winsorización
  - Creación de nuevas variables

- **Entrenamiento y validación de modelos**
  - Comparación entre **Random Forest** y **LightGBM**
  - Evaluación con **RMSE** en un conjunto de validación (`X_val`)
  - Selección del mejor modelo (**Random Forest** por defecto superó incluso al modelo tuneado)

- **Predicción final sobre conjunto de test**
  - El mejor modelo se entrena con todos los datos y genera el archivo `submission.csv`.

---

## 🛠 Requisitos

- Python ≥ 3.8
- Jupyter Notebook
- scikit-learn
- lightgbm
- numpy
- pandas
- matplotlib
- seaborn
- Cuenta de Kaggle y archivo `kaggle.json` en la raíz del proyecto

---

## 🚀 Cómo usar este proyecto

1. Asegúrate de tener el archivo `kaggle.json` en la misma carpeta que el notebook.
2. Ejecuta el notebook secuencialmente.
3. El modelo entrenado generará un archivo `submission.csv` con las predicciones.

---

## 📌 Notas adicionales

- No se utiliza Google Colab; el notebook está **100% adaptado para entorno local**.
- El tuning con `RandomizedSearchCV` reveló que el **Random Forest base** generaliza mejor que el modelo optimizado.
