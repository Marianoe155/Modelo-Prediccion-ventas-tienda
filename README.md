# 📊 BigMart Sales Prediction

![Python](https://img.shields.io/badge/Python-3.10-blue)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-green)
![Pandas](https://img.shields.io/badge/EDA-Pandas-yellow)
![Machine Learning](https://img.shields.io/badge/ML-Regression-orange)

> Modelo de Machine Learning para predecir ventas por producto en tiendas BigMart utilizando técnicas de regresión, feature engineering y XGBoost.

---

## 📌 Métricas del mejor modelo

| Métrica | Valor |
|----------|------|
| Modelo | XGBoost |
| RMSE | ~907 |
| R² CV | 0.594 |
| R² train | 0.583 |

---

## 🎯 Problema

Dado un dataset transaccional de ventas en una cadena de supermercados, el objetivo es predecir `Item_Outlet_Sales` y entender los factores que impactan en las ventas.

---

## 📁 Estructura del repositorio


```
PREDICCION_VENTAS_TIENDA/
├── data/
│   ├── Train_BigMart.csv           # Dataset de entrenamiento (8,523 filas)
│   ├── Test_BigMart.csv            # Dataset de test (5,681 filas)
│   ├── test_clean.csv              # Dataset de test limpia (5,681 filas)
│   ├── train_clean_sin_outl.csv    # Dataset de entrenamiento limpia sin outliers (5,681 filas)
│   └── train_clean.csv             # Dataset de entrenamiento limpia con outliers (5,681 filas)
├── entregables/ 
│   ├── README.html                  
│   └── test_predicciones.csv       # Predicciones sobre el test set
├── imagenes/                       # Gráficos generados por el notebook
├── modelo/
│   TEST.ipynb                      # Predicciones sobre el test set
├── notebooks/
│   ├── EDA.ipynb                   # Notebook principal (análisis + limpieza)
│   └── MODELADO.ipynb              # Notebook MODELO
└── requirements.txt                # Librerías
```

---

## 🧠 Metodología

### 🔹 Limpieza de datos
- Tratamiento de valores nulos (`Item_Weight`, `Outlet_Size`)
- Normalización de categorías (`LF` → `Low Fat`, etc.)

### 🔹 EDA
- Análisis de variables categóricas y numéricas
- Detección de outliers
- Boxplots y correlaciones

### 🔹 Feature Engineering

| Feature | Descripción |
|----------|-------------|
| `antiguedad` | Años desde apertura de la tienda |
| `precio_por_peso` | Relación precio vs peso |
| `producto_barato_caro` | Segmento por precio |
| `visibilidad_por_precio` | Relación visibilidad-precio |
| `clasificacion_visibilidad` | Segmentación por visibilidad |

### 🔹 Preparación del dataset
- Encoding de variables categóricas
- Eliminación de variables no útiles
- Comparación con y sin outliers

---

## 🤖 Modelado

### Modelos evaluados (Cross Validation 5-fold)

| Modelo | RMSE | R² |
|--------|------|----|
| Regresión Lineal | ~1068 | 0.580 |
| Random Forest | ~1103 | 0.552 |
| **XGBoost** | **~907** | **0.603** |

---

## 📊 Features más importantes

1. `producto_barato_caro`
2. `Outlet_Type`
3. `antiguedad`
4. `visibilidad_por_precio`

---

## 📈 Resultados

- RMSE: ~907.97  
- R² CV: 0.594  
- RMSE train: 939  
- R² train: 0.583  

→ El modelo muestra buena estabilidad y capacidad de generalización.

---

## 📉 Visualizaciones

### Importancia de variables

![Feature Importance](/imagenes/top_feature.png)

### Ajuste del modelo

![Model Performance](/imagenes/linea_modelo.png)

---

## 🧠 Insights

- El tipo de tienda (`Outlet_Type`) es uno de los factores más influyentes.
- El precio no es el principal driver de ventas en todos los casos.
- La antigüedad de la tienda tiene impacto positivo en ventas.
- La visibilidad del producto no muestra un impacto fuerte en el modelo.

---

## 🚀 Próximos pasos

→ Incorporar variables externas:
- Demografía del área de cada tienda
- Feriados y estacionalidad
- Promociones y descuentos

→ Mejoras de modelo:
- Optimización de hiperparámetros (Optuna / GridSearch)
- Feature selection más avanzada
- Ensambles (XGBoost + LightGBM)

---

## 👤 Autor

**Mariano Baigorria**  
🔗 [LinkedIn](https://www.linkedin.com/in/mariano-baigorria-b85004282/)