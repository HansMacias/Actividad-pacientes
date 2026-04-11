Análisis de Datos EEG y Predicción de Epilepsia con Árbol de Decisión
Este proyecto implementa un modelo de clasificación basado en un Árbol de Decisión para predecir la presencia de ataques epilépticos (Grupo 1) a partir de datos de electroencefalogramas (EEG).

Descripción del Proyecto
El objetivo principal de este notebook es analizar un conjunto de datos EEG, donde se registra la actividad cerebral de diferentes participantes, categorizados en dos grupos: 'Normal' (Grupo 0) y 'Epiléptico' (Grupo 1). Se utiliza un algoritmo de aprendizaje automático (Árbol de Decisión) para construir un modelo predictivo que pueda diferenciar entre estos dos estados basándose en las mediciones EEG.

Origen de los Datos
Los datos utilizados en este proyecto se cargan desde un archivo CSV alojado en GitHub:

DM.csv

Este archivo contiene mediciones de electrodos EEG (C3, C4, F3, F4, etc.), el minuto de la medición, un identificador de participante y la etiqueta del grupo (0 o 1).

Dependencias
Para ejecutar este notebook, necesitarás las siguientes librerías de Python:

pandas
scikit-learn
matplotlib
requests
Puedes instalarlas usando pip:

pip install pandas scikit-learn matplotlib requests
Uso
Descargar el Notebook: Clona este repositorio o descarga el archivo .ipynb.
Cargar los Datos: El notebook comienza descargando automáticamente el archivo DM.csv desde la URL proporcionada y cargándolo en un DataFrame de pandas.
Preprocesamiento: Las columnas irrelevantes ('Participante' y 'EMG') son eliminadas, y la columna 'Grupo' se define como la variable objetivo (y). El resto de las columnas EEG se utilizan como características (X).
División de Datos: Los datos se dividen en conjuntos de entrenamiento (80%) y prueba (20%) para evaluar el rendimiento del modelo.
Entrenamiento del Modelo: Se entrena un DecisionTreeClassifier con los datos de entrenamiento.
Evaluación: Se realizan predicciones sobre el conjunto de prueba y se evalúa el modelo utilizando:
Precisión (Accuracy)
Matriz de Confusión
Informe de Clasificación (Precision, Recall, F1-Score)
Visualización: Se genera una visualización del árbol de decisión entrenado, mostrando las reglas que el modelo ha aprendido para clasificar los grupos.
Resultados del Modelo (Ejemplo)
Después de ejecutar el modelo, se obtienen métricas de rendimiento. A continuación, se presenta un ejemplo de salida que verías en el notebook:

Precisión del modelo: 0.7833

Matriz de Confusión:

[[84 20]
 [19 57]]
Informe de Clasificación:

              precision    recall  f1-score   support

           0       0.82      0.81      0.81       104
           1       0.74      0.75      0.75        76

    accuracy                           0.78       180
   macro avg       0.78      0.78      0.78       180
weighted avg       0.78      0.78      0.78       180
Estos resultados indican que el modelo tiene una precisión general del 78.33%. La matriz de confusión muestra cuántas clasificaciones correctas e incorrectas se hicieron para cada clase, y el informe de clasificación proporciona métricas más detalladas como precisión, exhaustividad (recall) y puntuación F1 para cada grupo.