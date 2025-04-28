# 🏠 Predicción de precios de viviendas con Machine Learning

Este proyecto entrena y compara múltiples modelos de regresión para predecir el precio de venta (`Sold Price`) de propiedades residenciales, utilizando información estructural y contextual.

---

## 🛠️ Proceso aplicado

1. **Limpieza de datos**
   - Imputación de nulos con la mediana.
   - Eliminación de registros inválidos (`Listed Price = 0`).
   - Transformación de año de construcción a antigüedad (`House age`).

2. **Transformaciones**
   - Aplicación de `log1p()` a precios y superficie habitable.
   - Reducción de outliers con `.clip()`.

3. **Modelado**
   - Regresión Lineal
   - Random Forest
   - Gradient Boosting (sklearn)
   - XGBoost
   - LightGBM

4. **Optimización**
   - Se utilizó **`GridSearchCV` con LightGBM** para encontrar la mejor combinación de hiperparámetros.
   - El modelo final entrenado con estos parámetros fue el más preciso del proyecto.

---

## 📊 Resultados comparativos

| Modelo                   | Error relativo aprox. |
|--------------------------|------------------------|
| Regresión Lineal         | 27.82%                |
| Random Forest            | 24.63%                |
| Gradient Boosting        | 23.36%                |
| XGBoost                  | 23.47%                |
| LightGBM                 | 23.05%                |
| **LightGBM (GridSearch)**| **⬇️ 22.80%** ✅ Mejor resultado

---

## ✅ Conclusiones

- El modelo **LightGBM con ajuste de hiperparámetros** fue el mejor predictor de precios, alcanzando un error relativo de solo **22.41%**.
- Las técnicas de **preprocesamiento y transformación logarítmica** fueron claves para estabilizar el entrenamiento y mejorar la precisión.
- El uso de `GridSearchCV` permitió afinar el modelo final y obtener mejores resultados que con configuraciones por defecto.

---

## 📁 Archivos incluidos

- `precio_de_casas listo.ipynb`: Notebook completo con limpieza, modelado, evaluación y optimización final con `GridSearchCV`.

---
