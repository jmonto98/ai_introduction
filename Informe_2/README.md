# Actividad 2 – Machine Learning Supervisado

## Integrantes
- Daniel Posada – dposad21@eafit.edu.co
- John Montoya – jmonto98@eafit.edu.co

Repositorio público: [Informe 2](https://github.com/jmonto98/ai_introduction/tree/main/Informe_2)  

---
## Estructura del Proyecto

```
Informe_2
├── data
│   └── heart.csv
├── notebooks
│   └── analisis_heart_disease.ipynb
├── README.md
└── requirements.txt
```
---
## 1. Descripción del dataset

**Fuente:** [Heart Disease UCI (Kaggle)](https://www.kaggle.com/ronitf/heart-disease-uci)  

**Registros:** 1025 pacientes  
**Variables:** 14 columnas totales, que incluyen datos clínicos como edad, sexo, presión arterial, colesterol, etc.

**Objetivo del problema:**  
Predecir si un paciente presenta **enfermedad cardíaca**.  
La variable objetivo es **`target`**:
- `1` = presencia de enfermedad cardíaca
- `0` = no presenta enfermedad

---

## 2. Preprocesamiento

1. **Limpieza de datos:**  
   - Se identificaron y trataron valores faltantes utilizando `SimpleImputer`:
     - Numéricos: imputación con la mediana.
     - Categóricos: imputación con la moda.

2. **Codificación de variables categóricas:**  
   - `OneHotEncoder` para convertir variables categóricas en variables dummy.

3. **Escalado/normalización:**  
   - `StandardScaler` para las variables numéricas, necesario para que la Red Neuronal y KNN trabajen con datos en la misma escala.

4. **División en train/test:**  
   - 70 % de los datos para entrenamiento y 30 % para prueba, con estratificación de la variable objetivo para mantener la proporción de clases.

---

## 3. Modelos entrenados

### 3.1 Modelo clásico: **Random Forest**
- `n_estimators`: 200
- `random_state`: 42
- Random Forest entrenado con n_estimators=200 (200 árboles) sobre el 70 % de los 1025 registros de entrenamiento.


### 3.2 Red Neuronal (MLP – Keras)
- Capas:  
  - Capa densa de 16 neuronas (ReLU)  
  - Capa densa de 8 neuronas (ReLU)  
  - Capa de salida de 1 neurona (Sigmoid)
- Optimizador: Adam
- Pérdida: `binary_crossentropy`
- Épocas: 50
- Batch size: 16

### 3.3 Algoritmo adicional: **k-Nearest Neighbors (KNN)**
- `n_neighbors`: 5
- Distancia: Euclídea.

---

## 4. Evaluación de resultados

| Modelo          | Accuracy | F1-score |
|------------------|---------|---------|
| Random Forest    | **0.990** | **0.990** |
| Red Neuronal     | 0.948   | 0.946* |
| KNN              | 0.854   | 0.856 |

\*El F1 de la red neuronal se calculó con `sklearn.metrics.f1_score` después del entrenamiento.

**Otras visualizaciones:**
- Matriz de confusión de cada modelo.
- Curva de pérdida (train/val) de la red neuronal.
- Importancia de variables en el Random Forest.

---

## 5. Análisis comparativo

| Modelo | Ventajas | Desventajas |
|-------|---------|------------|
| **Random Forest** | Alta exactitud y F1, robusto al ruido, identifica importancia de variables. | Modelo más pesado, menos interpretable que un solo árbol. |
| **Red Neuronal** | Buena capacidad de generalización, flexible para relaciones no lineales. | Requiere más tiempo de entrenamiento y ajuste de hiperparámetros. |
| **KNN** | Sencillo de implementar, no necesita entrenamiento explícito. | Menor desempeño, sensible a la escala y al número de vecinos. |

**Conclusión del comparativo:**  
Random Forest superó a los otros dos modelos en todas las métricas, mostrando un equilibrio casi perfecto entre precisión y recall. La Red Neuronal también tuvo un buen desempeño, mientras que KNN quedó rezagado.

---

## 6. Conclusiones

- El proceso de **preprocesamiento** (imputación, codificación y escalado) es clave para que los tres algoritmos trabajen en igualdad de condiciones.
- **Random Forest** resultó ser la técnica más adecuada para este dataset, logrando un F1 del 99 %.
- La **Red Neuronal** alcanzó un rendimiento alto (94–95 %) pero requirió mayor ajuste de hiperparámetros.
- **KNN**, aunque fácil de entender e implementar, mostró la menor precisión.
- Esta práctica permitió comprender la importancia de comparar distintos modelos supervisados y de evaluar con métricas más completas que solo la accuracy, como el **F1-score**.

---

## 7. Requisitos para reproducir

**Dependencias principales:**
```
pandas
numpy
scikit-learn
tensorflow
matplotlib
```

**Ejecución:**
1. Clonar el repositorio:
   ```bash
   git clone https://github.com/jmonto98/ai_introduction.git
   cd Informe_2
   ```

2. Instalar dependencias:
   ```bash
   pip install -r requirements.txt
   ```

3. Abrir el notebook:
   ```bash
   jupyter notebook notebooks/analisis_heart_disease.ipynb
   ```
---

## 8. Referencias

* [Dataset: Heart Disease UCI – Kaggle](https://www.kaggle.com/ronitf/heart-disease-uci)
* [Scikit-learn documentation](https://scikit-learn.org/)
* [TensorFlow Keras documentation](https://www.tensorflow.org/guide/keras)

---