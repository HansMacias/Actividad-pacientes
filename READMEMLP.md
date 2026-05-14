# Proyecto de Clasificación de Datos EEG con MLP

Este notebook presenta un análisis de clasificación de datos de Electroencefalografía (EEG) utilizando un Perceptrón Multi-Capa (MLP). El objetivo principal es clasificar los datos en diferentes grupos basándose en las señales EEG.

## Pasos Realizados

1.  **Carga de Datos:** Los datos se cargaron desde un archivo CSV alojado en GitHub, que contiene mediciones de diversos canales EEG, junto con información de grupo y participante.
    *   Fuente de Datos: `https://raw.githubusercontent.com/Fernoguez/EEG/main/DM.csv`

2.  **Preprocesamiento de Datos:**
    *   Se identificó 'Grupo' como la variable objetivo (`y`) y los canales EEG como características (`X`).
    *   Se dividieron los datos en conjuntos de entrenamiento (80%) y prueba (20%) con `stratify=y` para mantener la proporción de clases.
    *   **Manejo de Valores Faltantes:** Se utilizó `SimpleImputer` con estrategia de media para rellenar los valores `NaN` presentes en las características.
    *   **Escalado de Características:** `StandardScaler` se aplicó para normalizar las características, lo cual es crucial para el buen rendimiento de los MLPs.

3.  **Entrenamiento del Modelo MLP:**
    *   Se configuró un `MLPClassifier` con dos capas ocultas (100 y 50 neuronas, respectivamente), función de activación 'relu' y optimizador 'adam'.
    *   El modelo fue entrenado exitosamente con los datos preprocesados.

4.  **Evaluación del Modelo:**
    *   El modelo se evaluó en el conjunto de prueba, obteniendo métricas de rendimiento clave.
    *   Se generó un `classification_report` detallado y se calculó la precisión.
    *   Las predicciones del modelo, junto con las etiquetas reales del conjunto de prueba, se guardaron en un archivo CSV (`eeg_mlp_predictions.csv`) descargable.

5.  **Análisis de Importancia de Características:**
    *   Se calculó la importancia de permutación (Permutation Feature Importance) para identificar qué canales EEG son más influyentes en las predicciones del modelo. Esto proporciona una visión sobre la relevancia de cada canal para la clasificación.

## Resultados Clave

*   **Precisión (Accuracy):** El modelo MLP alcanzó una precisión del **91.67%** en el conjunto de prueba.
*   **Informe de Clasificación:** El informe mostró un buen desempeño para ambas clases (0 y 1), con F1-scores de 0.93 para la clase 0 y 0.90 para la clase 1, lo que indica un equilibrio entre precisión y recall.
*   **Importancia de Canales EEG:** El análisis de importancia de características reveló que canales como `F3`, `T6` y `F8` son los más importantes para el modelo en la clasificación de los datos.

## Cómo ejecutar el Notebook

1.  Abre este notebook en Google Colab o cualquier entorno compatible con Jupyter.
2.  Asegúrate de tener instaladas las librerías necesarias (pandas, scikit-learn, matplotlib, seaborn).
3.  Ejecuta todas las celdas en orden. El notebook cargará los datos automáticamente, realizará el preprocesamiento, entrenará el modelo, lo evaluará y generará el gráfico de importancia de características.
