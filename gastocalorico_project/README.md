# 🔥 Predicción del Gasto Calórico con Machine Learning

Este proyecto tiene como objetivo predecir el gasto calórico de individuos utilizando técnicas de regresión aplicadas a un conjunto de datos proporcionado por una competencia de Kaggle. Se exploran múltiples modelos y técnicas de preprocesamiento para lograr el mejor rendimiento posible.

---

## 📁 Estructura del proyecto

- `gasto_calorico.ipynb`: Notebook principal con todo el pipeline implementado.
- `train.csv`: Datos de entrenamiento.
- `test.csv`: Datos de prueba para predicción.
- `submission.csv`: Archivo generado con las predicciones para Kaggle.

---

## ⚙️ Proceso general

1. **Carga y análisis exploratorio**
   - No se encontraron valores nulos en los datos.
   - Se realizaron análisis gráficos para entender las relaciones entre variables.

2. **Preprocesamiento**
   - Tratamiento de outliers utilizando **winsorizing por IQR**.
   - Conversión de variables categóricas (por ejemplo, `Sex`) a formato numérico.
   - Creación de nuevas variables derivadas como **IMC (Índice de Masa Corporal)**.

3. **Selección de características**
   - Se evaluaron las correlaciones entre variables y se aplicó ingeniería de características.
   - Se eliminaron algunas columnas como `Height` y `Weight` tras crear la columna `IMC`.

4. **Entrenamiento y evaluación de modelos**
   Se entrenaron y compararon los siguientes modelos usando validación cruzada:

   | Modelo                   | RMSE   | MAE   | R²     |
   |--------------------------|--------|-------|--------|
   | Linear Regression        | 11.12  | 8.10  | 0.9681 |
   | Random Forest            | 4.46   | 2.81  | 0.9949 |
   | Lasso Regression (scaled)| 11.13  | 8.08  | 0.9681 |
   | Gradient Boosting        | 5.10   | 3.44  | 0.9933 |
   | CatBoost Regressor       | 3.97   | 2.47  | 0.9959 |
   | **Stacking Regressor**   | 3.97   | 2.46  | 0.9959 |

   > ✅ El mejor desempeño fue obtenido por el **Stacking Regressor**, con un excelente R² y bajo error.

5. **Modelo final y predicción**
   - Se entrenó el modelo final (Stacking Regressor) con todo el `df_train`.
   - Se aplicaron predicciones sobre `df_test`.
   - Se forzaron los valores negativos a cero debido a la métrica utilizada por Kaggle (MSLE).

---

## 📈 Modelo utilizado para `submission`

```python
final_model = StackingRegressor(...)
final_model.fit(X, y)
predictions = np.maximum(final_model.predict(X_test), 0)
