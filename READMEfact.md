```markdown
# README: Análisis de Funciones de Activación en Datos EEG

## Descripción del Proyecto
Este notebook tiene como objetivo demostrar la aplicación de cinco funciones de activación comúnmente utilizadas en redes neuronales (ReLU, Sigmoid, Softmax, Tanh, y Leaky ReLU) a un conjunto de datos de EEG. Se carga un archivo `.docx` para identificar las funciones de activación y luego se procesa un archivo CSV que contiene los datos de EEG.

## Configuración y Datos

### Dependencias
Se requiere la librería `python-docx` para leer documentos `.docx`:
```bash
pip install python-docx
```

### Carga de Datos
Los datos de EEG se cargan directamente desde un repositorio de GitHub utilizando `pandas`. El archivo CSV se encuentra en: `https://raw.githubusercontent.com/Fernoguez/EEG/main/DM.csv`.

### Documento de Funciones de Activación
El notebook lee las funciones de activación de un archivo `funciones de activacion.docx` para contextualizar el análisis.

## Funciones de Activación Implementadas
Las siguientes funciones de activación son definidas y aplicadas a la columna 'C3' del DataFrame de EEG:
1.  **ReLU** (Rectified Linear Unit)
2.  **Sigmoid** (Función Logística)
3.  **Softmax** (Función Softmax) - _Nota: Su aplicación a una única columna aquí es demostrativa y no su uso canónico para clasificación multiclase._
4.  **Tanh** (Tangente Hiperbólica)
5.  **Leaky ReLU** (Leaky Rectified Linear Unit)

## Análisis y Resultados
El notebook aplica cada una de las funciones definidas a la columna 'C3' del DataFrame, generando nuevas columnas para cada transformación. Un análisis detallado en las celdas de texto describe cómo cada función afecta los valores de 'C3', considerando que los valores originales son positivos y oscilan entre 1.3 y 1.5. Se discuten las implicaciones de cada transformación, especialmente en el contexto de un posible uso en redes neuronales.

Los resultados muestran que:
-   **ReLU** no altera los valores, ya que todos son positivos.
-   **Sigmoid** comprime los valores a un rango estrecho entre 0 y 1, mostrando saturación.
-   **Softmax** genera valores extremadamente pequeños, lo cual se explica por su aplicación no estándar a una única columna.
-   **Tanh** y **Leaky ReLU** también transforman los valores de 'C3' de maneras específicas, con Leaky ReLU comportándose de manera similar a ReLU para valores positivos, pero con la capacidad de manejar entradas negativas sin producir cero.

## Uso
Este notebook puede ser utilizado como una referencia para entender el comportamiento individual de las funciones de activación cuando se aplican a datos numéricos. Los usuarios pueden modificar la `input_column` para experimentar con otras columnas de sus propios DataFrames o ajustar las funciones para adaptarse a diferentes escenarios.

```
