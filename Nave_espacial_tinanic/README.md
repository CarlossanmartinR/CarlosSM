# 🪐 Nave Espacial Titanic - Clasificación de Pasajeros

Este proyecto busca predecir si un pasajero fue transportado al hiperespacio en la nave espacial *Titanic*, utilizando modelos de clasificación entrenados con datos provistos por la competencia de Kaggle.

---

## 📁 Contenido

- `Nave_espacial_titanic.ipynb`: notebook con todo el flujo de trabajo:
  - Análisis exploratorio
  - Ingeniería de características
  - Imputación de datos
  - Escalado y normalización
  - Entrenamiento y evaluación de modelos
  - Ensamble de los mejores modelos (VotingClassifier)
  - Generación del archivo `submission.csv` para Kaggle

---

## 🧠 Flujo del Proyecto

### 1. Carga de Datos

- Lectura de los archivos `train.csv` y `test.csv` desde Kaggle.

### 2. Análisis Exploratorio

- Análisis de distribución, nulos y correlaciones.
- Visualización de datos y outliers con boxplots y heatmaps.

### 3. Ingeniería de Características

- Se creó `TotalServices` sumando los gastos individuales:
  - `RoomService`, `FoodCourt`, `ShoppingMall`, `Spa`, `VRDeck`
- Se extrajo la columna `Deck` desde `Cabin`.

### 4. Limpieza de Datos

- Imputación de datos numéricos con **mediana del conjunto de entrenamiento**.
- Imputación de datos categóricos con **moda del conjunto de entrenamiento**.
- Aplicación de Winsorization para tratar outliers detectados por el método IQR.

### 5. Codificación

- Se aplicó **one-hot encoding** (`pd.get_dummies`) a las variables categóricas.

### 6. Escalado

- Se usó `StandardScaler` exclusivamente en el modelo **SVM**, ya que es sensible a la escala de los datos.

---

## 🤖 Modelos Evaluados

| Modelo            | Accuracy  |
|-------------------|-----------|
| SVM               | 0.786659  |
| LightGBM          | 0.780334  |
| XGBoost           | 0.770558  |
| Random Forest     | 0.759632  |
| Decision Tree     | 0.719954  |

---

## 🏆 Voting Classifier

- Se seleccionaron los **3 mejores modelos**:
  - SVM
  - LightGBM
  - XGBoost

- Se aplicó un **VotingClassifier** con `voting='hard'`:
  - Accuracy alcanzada: **0.786659**
  - Este ensamble fue usado para generar el archivo de envío a Kaggle.

---

## 📤 Envío a Kaggle

- Se generó `submission.csv` con las predicciones del VotingClassifier.
- Las predicciones fueron ordenadas según el `PassengerId`.

---

## 🛠️ Herramientas y Librerías

- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `scikit-learn`
- `lightgbm`
- `xgboost`

---

## 📌 Notas Finales

- El escalado y la imputación se realizaron correctamente solo con datos de entrenamiento.
- Se evaluaron múltiples estrategias antes de optar por ensamble.
- El pipeline completo está optimizado para evitar data leakage y mantener consistencia entre `train` y `test`.

---

## 🤝 Autor

Proyecto desarrollado como práctica de aprendizaje automático para mejorar habilidades en Kaggle y modelos de clasificación.
