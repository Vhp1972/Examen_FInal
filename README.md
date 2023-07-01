# Examen_FInal
Tratamiento de datos - CarneDataset
- os: Para manipular rutas de archivos y directorios.
- cv2: Para leer y manipular imágenes.  
	pip install opencv-contrib-python
	pip install matplotlib
- numpy as np: Para trabajar con matrices y vectores de manera eficiente.
- LabelEncoder de sklearn.preprocessing: Para codificar las etiquetas como números.
- train_test_split de sklearn.model_selection: 
	Para dividir el conjunto de entrenamiento en entrenamiento y validación.
- confusion_matrix de sklearn.metrics: 
	Para calcular las matrices de confusión.
- Sequential de tensorflow.keras.models: 
	Para definir una secuencia lineal de capas en el modelo.
- Conv2D, MaxPooling2D, Flatten, Dense de tensorflow.keras.layers: 
	Para agregar capas convolucionales, de agrupamiento, de aplanamiento y completamente 	conectadas al modelo.

Definición de las rutas de las carpetas de entrenamiento y prueba.

Lectura de imágenes de entrenamiento y sus etiquetas:
	train_folder = 'CarneDataset/train'
	test_folder = 'CarneDataset/test'
Se recorren las carpetas de entrenamiento y se leen las imágenes utilizando cv2.imread().
Se almacenan las imágenes y las etiquetas en listas separadas.
Conversión de las listas de imágenes y etiquetas a matrices NumPy.
Codificación de las etiquetas como números utilizando LabelEncoder de sklearn.preprocessing.
División del conjunto de entrenamiento en entrenamiento y validación utilizando train_test_split de sklearn.model_selection.
Normalización de los valores de píxeles de las imágenes en el rango [0, 1] dividiendo por 0. 255.

Definición de la arquitectura del modelo de red convolucional (CNN):
- Se utiliza un modelo secuencial (Sequential) de tensorflow.keras.models.
- Se agregan capas convolucionales (Conv2D) con activación ReLU y capas de agrupamiento (MaxPooling2D).
- Se agrega una capa de aplanamiento (Flatten) para convertir los mapas de características en un vector.
- Se agregan capas densas (Dense) con activación ReLU y una capa densa final con activación softmax para la clasificación multiclase.
- Se compila el modelo con el optimizador 'adam' y la función de pérdida 'sparse_categorical_crossentropy'.
- Se entrena el modelo utilizando fit de tensorflow.keras.models.
- Se proporcionan los datos de entrenamiento, las etiquetas codificadas, el número de épocas y el tamaño del lote.
- Se proporcionan los datos de validación para monitorear el rendimiento durante el entrenamiento.

Lectura de imágenes de prueba y sus etiquetas, de manera similar a la lectura de imágenes de entrenamiento.

Normalización de los valores de píxeles de las imágenes de prueba.
Realización de predicciones en el conjunto de prueba utilizando el método predict del modelo.
Decodificación de las etiquetas predichas y cálculo de la matriz de confusión del modelo utilizando confusion_matrix de sklearn.metrics.
Cálculo de la matriz de confusión del error en entrenamiento utilizando los datos de entrenamiento y las predicciones del modelo.
Cálculo de la matriz de confusión del error en prueba utilizando los datos de prueba y las predicciones del modelo.

Impresión de las matrices de confusión.

Se carga las imágenes de entrenamiento y prueba, entrenar un modelo de red convolucional, realizar predicciones en el conjunto de prueba y calcular las matrices de confusión para evaluar el rendimiento del modelo.

Observacion: Trabajo en grupo 
