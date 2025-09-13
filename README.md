# AI Introduction

## Descripción general

Este repositorio contiene los trabajos del curso *Introducción a la Inteligencia Artificial / Machine Learning*, realizados por [**dposad13**](https://github.com/dposada13) y [**jmonto98**](https://github.com/jmonto98).
Incluye informes, notebooks y ejemplos prácticos de los principales conceptos vistos en clase.

---

## Contenido del repositorio
```
.
├── Informe_1 - Primer informe del curso. Incluye ejercicios, análisis y resultados de modelos básicos.
│   ├── Ejercicio_1
│   │   ├── BestFirstSearch.ipynb
│   │   └── README.md
│   ├── Ejercicio_2
│   │   ├── Big_maze.ipynb
│   │   ├── Maze_problem.ipynb
│   │   └── README.md
│   ├── Ejercicio_3
│   │   ├── README.md
│   │   └── Subway.ipynb
│   ├── README.md
│   └── requirements.txt
├── Informe_2 - Segundo informe del curso. Con trabajos más avanzados, comparativas de algoritmos, experimentos adicionales.
│   ├── data
│   │   └── heart.csv
│   ├── notebooks
│   │   └── analisis_heart_disease.ipynb
│   └── requirements.txt
└── README.md
```

---

## Objetivos

- Aplicar los conceptos teóricos de aprendizaje supervisado (y posiblemente no supervisado) a datasets reales.  
- Efectuar preprocesamiento de datos: limpieza, codificación, normalización, división train/test.  
- Entrenar varios modelos de Machine Learning, comparar su rendimiento y presentar conclusiones basadas en métricas relevantes.  
- Desarrollar habilidades de análisis de datos, visualización y redacción científica/informal (informes).

---

## Tecnologías y librerías usadas

- Python  
- Jupyter Notebook  
- Pandas  
- Scikit-learn  
- Matplotlib / Seaborn  
- Otras librerías auxiliares según informe (por ejemplo, TensorFlow/Keras, XGBoost, etc.)

---

## Instalación

### 1. Clonar el repositorio

```sh
git clone https://github.com/tu_usuario/ai_introduction.git
cd ai_introduction
```

### 2. Crear un entorno virtual

#### Windows

```sh
python -m venv .venv
.venv\Scripts\activate
```

#### macOS / Linux

```sh
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Instalar dependencias

```sh
# Navega al folder correspondiente
cd Informe_x
pip install -r requirements.txt
```

### 4. Ejecutar los notebooks

```sh
jupyter notebook
```

## Notas

- Si no tienes `virtualenv` ni `jupyter`, instálalos con:
  ```sh
  pip install virtualenv jupyter
  ```
- Para salir del entorno virtual:  
  - Windows: `deactivate`  
  - macOS/Linux: `deactivate`

---