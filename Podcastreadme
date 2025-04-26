🧠 Predict Podcast Listening Time – Machine Learning con Jupyter
Este proyecto aborda el desafío de predecir el tiempo de escucha de episodios de podcast, utilizando técnicas de aprendizaje automático. El trabajo se realizó en Jupyter Notebook e incluye análisis de datos, preprocesamiento, tuning de modelos y generación de predicciones para envío.

📂 Contenido del notebook
1. Carga de datos desde Kaggle API
El notebook está diseñado para funcionar localmente, leyendo el archivo kaggle.json

2. Exploración y limpieza de datos

Análisis de valores nulos

Transformación de variables categóricas

Detección de outliers y winsorización

Creación de nuevas variables

3. Entrenamiento y validación de modelos

Comparación entre Random Forest y LightGBM

Evaluación con RMSE en un conjunto de validación (X_val)

Selección del mejor modelo (Entre Random forest, LightGBM y Random forest con randomized)

4. Predicción final sobre conjunto de test
El mejor modelo (Random Forest con hiperparámetros por defecto en este caso) se entrena con todos los datos y se utiliza para predecir el conjunto de test.

5. Exportación de resultados
Se genera un archivo submission.csv listo para envío a Kaggle.

🛠 Requisitos
Python ≥ 3.8

Jupyter Notebook

scikit-learn, lightgbm, numpy, pandas, matplotlib, seaborn

Cuenta de Kaggle y archivo kaggle.json en la raíz del proyecto

🚀 Cómo usar este proyecto
Asegúrate de tener el archivo kaggle.json en la misma carpeta que el notebook.

Ejecuta el notebook secuencialmente.

El modelo entrenado generará un archivo submission.csv con las predicciones.

📌 Notas adicionales
No se utiliza google.colab, el notebook está 100% adaptado para entorno local.

El tuning con RandomizedSearchCV reveló que el modelo base de Random Forest generaliza mejor que la versión optimizada.
