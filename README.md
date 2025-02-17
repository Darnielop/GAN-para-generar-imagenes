# GAN para Generar Imágenes de Prendas y Accesorios

Este repositorio contiene una implementación de una Red Generativa Antagónica (GAN) utilizando Keras para generar imágenes de prendas y accesorios basadas en el dataset [Fashion MNIST](https://github.com/zalandoresearch/fashion-mnist). La idea es entrenar un modelo que, a partir de ruido aleatorio, genere imágenes que se asemejen a prendas de vestir reales.

## Descripción

La GAN consta de dos modelos principales:
- **Generador:** Crea imágenes a partir de vectores de ruido.
- **Discriminador:** Distingue entre imágenes reales (del dataset) e imágenes generadas.

El notebook `GAN_para_generar_imágenes_de_prendas_y_accesorios.ipynb` incluye todo el código para entrenar el modelo, visualizar la evolución durante el entrenamiento y generar nuevas imágenes.

> **Nota:** Para reducir el tiempo de entrenamiento, se ha incluido la opción de utilizar solo una fracción del dataset (por ejemplo, 10,000 o 5,000 imágenes) en lugar de las 60,000 originales. Puedes modificar la variable `subset_size` en el notebook para ajustar este parámetro.

## Requisitos

- Python 3.6+
- [TensorFlow](https://www.tensorflow.org/) (incluye Keras)
- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)
- Jupyter Notebook

## Uso

1. Carga del dataset:
El notebook descarga el dataset Fashion MNIST de Keras. Si deseas entrenar con menos datos, localiza la siguiente sección:

fashion_mnist = keras.datasets.fashion_mnist
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()
Y modifícala para usar solo una fracción, por ejemplo:

subset_size = 10000  # O 5000, según lo que desees usar
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()
train_images, train_labels = train_images[:subset_size], train_labels[:subset_size]

2. Entrenamiento:
Ejecuta las celdas del notebook en orden. Se recomienda ajustar los hiperparámetros (número de épocas, tasa de aprendizaje, tamaño del batch) para obtener mejores resultados.

3. Generación de Imágenes:
Una vez entrenado el modelo, se generarán imágenes de prendas y accesorios. Si los resultados no son los esperados, prueba:

- Aumentar el número de épocas.
- Ajustar la tasa de aprendizaje.
- Revisar la normalización de los datos.

## Parámetros y Ajustes

- subset_size: Define cuántas imágenes del dataset utilizar para el entrenamiento.
- num_epochs: Número de épocas de entrenamiento.
- batch_size: Tamaño del batch.
- learning_rate (lr): Tasa de aprendizaje para el optimizador.

## Resultados
Durante el entrenamiento se muestran ejemplos de imágenes generadas, lo que te permite evaluar el progreso del modelo. Si las imágenes no son satisfactorias, considera:

- Entrenar por más tiempo.
- Ajustar la arquitectura del generador y discriminador.
- Ajsutar los parámetros
