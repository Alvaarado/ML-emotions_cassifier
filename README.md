# Predicción de Nivel de Toxicidad en Textos utilizando modelos de machine learning

## Descripción del Proyecto

Este proyecto de machine learning tiene como objetivo identificar el nivel de toxicidad en comentarios de texto utilizando para ello técnicas de procesamiento de lenguaje natural (NLP) y diversos modelos de clasificación multietiqueta. A través de este análisis, pretendemos desarrollar un sistema capaz de clasificar comentarios de manera efectiva, lo cual puede ser útil en tareas como la moderación de contenido.

## Estructura del Proyecto

La estructura de carpetas es la siguiente:

1. **data**: Contiene los datos utilizados en el proyecto. Incluye los conjuntos de datos crudos y procesados.
2. **notebooks**: Almacena los archivos Jupyter Notebook que contienen el desarrollo del proyecto, desde la exploración de datos hasta la implementación de los modelos.
3. **models**: Incluye los archivos relacionados con los modelos entrenados, como los pesos y las configuraciones de los modelos.
4. **app**: Contiene los archivos necesarios para desplegar el modelo usando herramientas como Streamlit y Gradio, permitiendo la interacción con el modelo a través de una interfaz web.
5. **docs**: Aquí se encuentran las presentaciones realizadas durante el proyecto, donde se detallan tanto el progreso como los resultados obtenidos.

## Conclusiones

### Primer Modelo: Red Neuronal Recurrente (RNN) Bidireccional LSTM

Este modelo inicial fue entrenado sin ningún preprocesamiento de datos, actuando como una línea de referencia. Se trata de una red neuronal recurrente con una arquitectura bidireccional LSTM para la clasificación multietiqueta. 

**Resultados**:  
El modelo tuvo un buen rendimiento general, especialmente en la identificación de comentarios tóxicos. La precisión y recall fueron altos, lo que indica que la red neuronal fue capaz de identificar correctamente la mayoría de los comentarios tóxicos. Sin embargo, tuvo dificultades en la precisión categórica, mostrando limitaciones en la diferenciación entre algunas categorías específicas.

### Segundo Modelo: Regresión Logística Multinomial con TF-IDF

Este modelo utiliza un vectorizador TF-IDF y un clasificador de regresión logística multinomial para la clasificación de textos.

**Resultados**:  
El modelo mostró un rendimiento sólido en etiquetas frecuentes como "toxic" y "obscene". Sin embargo, las etiquetas menos comunes, como "severe_toxic", "threat", e "identity_hate", tuvieron bajos valores de recall. A pesar de los buenos resultados globales, el modelo requiere mejoras para manejar mejor las etiquetas infrecuentes.

### Tercer Modelo: Regresión Logística Multinomial con TF-IDF y Filtrado de Palabras Frecuentes

Este modelo es una versión iterada del segundo, en el cual se eliminaron las palabras más comunes del inglés durante la vectorización.

**Resultados**:  
Los resultados mostraron mínimas diferencias respecto al modelo anterior, sugiriendo que la eliminación de palabras comunes tuvo un impacto insignificante en el rendimiento general.

### Cuarto Modelo: Clustering KMeans

Este modelo utiliza KMeans para agrupar los comentarios en clusters similares según su contenido textual. Se trata, por tanto, del único de los cinco modelos realizados que presenta un enfoque no supervisado.

**Resultados**:  
Las métricas indicaron que los clusters no estaban bien definidos, con superposición significativa entre ellos. A pesar de esto, el modelo reveló algunas estructuras interesantes en los datos, pero requiere ajustes en los parámetros o preprocesamiento adicional para mejorar la calidad del clustering.

### Quinto Modelo: Regresión Logística Multinomial con TF-IDF

Este modelo es similar a los anteriores, pero con pequeños ajustes en los hiperparámetros.

**Resultados**:  
El rendimiento fue nuevamente bueno en las etiquetas más frecuentes, pero continuó mostrando dificultades en etiquetas menos comunes como "severe_toxic", "threat", e "identity_hate". Los resultados sugieren que se podrían obtener mejoras significativas mediante el uso de modelos más avanzados como redes neuronales recurrentes o transformers.

---

¡Gracias por usar Masterchef! Si tienes alguna pregunta, sugerencia o necesitas ayuda adicional, no dudes en contactar conmigo a traves de ruizfdezalvaro@gmail.com

---