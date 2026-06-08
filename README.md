# Asistente de conducción basado en Inteligencia Artificial 🚗🧠

Proyecto desarrollado como Trabajo de Fin de Máster. Este repositorio contiene la parte del entrenamiento de una red neuronal capaz de detectar señales de tráfico en imágenes y preparar el modelo para su posible uso dentro de un sistema de asistencia a la conducción.

<p align="justify">Aquí se puede encontrar el flujo de trabajo seguido para preparar el conjunto de datos, convertir las anotaciones al formato requerido por YOLO, entrenar un modelo de detección de señales de tráfico y exportar el modelo entrenado a formatos más ligeros para su posterior integración.</p>

## 🧾 Preparación del conjunto de datos 🧾

<p align="justify">El proyecto parte de conjuntos de imágenes de señales de tráfico. Para poder entrenar el modelo correctamente, las imágenes y sus anotaciones deben adaptarse al formato utilizado por YOLO. En este proceso se generan las etiquetas, se organizan las imágenes y se separa el conjunto de datos en entrenamiento, validación y prueba.</p>

## 🏷️ Conversión de anotaciones a formato YOLO 🏷️

<p align="justify">El archivo <b>gt-to-YOLO.ipynb</b> contiene el proceso de conversión de las anotaciones originales del GTSRB - German Traffic Sign Recognition Benchmark al formato de YOLO. Para cada imagen se genera un archivo de texto con las clases detectadas y las coordenadas normalizadas de las cajas delimitadoras.</p>

<p align="justify">Este paso es necesario porque YOLO trabaja con una estructura concreta de etiquetas, donde cada línea representa una señal detectada dentro de una imagen.</p>

## 🖼️ Conversión de imágenes 🖼️

<p align="justify">El archivo <b>ppm-to-jpg.ipynb</b> contiene funciones para convertir las imágenes del GTSRB en formato <b>.ppm</b> a <b>.jpg</b>. Este proceso facilita el manejo del conjunto de datos y mejora la compatibilidad con herramientas habituales de entrenamiento y visualización.</p>

## 📂 Creación del dataset YOLO 📂

<p align="justify">El archivo <b>dataset.ipynb</b> organiza el conjunto de datos en las carpetas necesarias para entrenar el modelo. En concreto, crea la estructura de imágenes y etiquetas para los subconjuntos de <b>train</b>, <b>val</b> y <b>test</b> para el GTSRB.</p>

## 🧠 Entrenamiento del modelo YOLO 🧠

<p align="justify">El archivo <b>yolo.ipynb</b> contiene el entrenamiento del modelo de detección de objetos. El modelo empleado se basa en YOLO y se entrena para reconocer diferentes tipos de señales de tráfico.</p>

<p align="justify">El entrenamiento se realiza utilizando la librería <b>Ultralytics</b>, que permite cargar modelos YOLO preentrenados, ajustar el número de clases del problema y guardar los resultados del entrenamiento.</p>

## 📱 Exportación del modelo 📱

<p align="justify">El archivo <b>tflite_export.ipynb</b> contiene el proceso de exportación del modelo entrenado a formatos más ligeros, como <b>TensorFlow Lite</b>. Este tipo de formato es útil cuando se quiere ejecutar el modelo en dispositivos con menos recursos computacionales, como puede ser la aplicación Android, segunda parte de este proyecto.</p>

## ⚙️ Configuración del entrenamiento ⚙️

<p align="justify">Se han utilizado los siguientes parámetros de entrenamiento:</p>

   - <p align="justify">epochs = 100</p>

   - <p align="justify">imgsz = 640</p>

   - <p align="justify">batch = 16</p>

   - <p align="justify">patience = 20</p>
   
## 📂 Disposición de los archivos del repositorio 📂

Aquí debajo se explica brevemente qué contiene cada archivo principal del repositorio:

   - <p align="justify"><b>README.md</b> es este archivo, con la información general del repositorio.</p>

   - <p align="justify"><b>LICENSE</b> con licencia Creative Commons CC0 1.0 Universal.</p>

   - <p align="justify"><b>gt-to-YOLO.ipynb</b> convierte las anotaciones originales del dataset GTSRB al formato requerido por YOLO.</p>

   - <p align="justify"><b>ppm-to-jpg.ipynb</b> convierte imágenes en formato <b>.ppm</b> a formato <b>.jpg</b>.</p>

   - <p align="justify"><b>dataset.ipynb</b> crea la estructura final del conjunto de datos del GTSRB, separando las imágenes y etiquetas en entrenamiento, validación y prueba.</p>

   - <p align="justify"><b>yolo.ipynb</b> contiene el entrenamiento del modelo YOLO para la detección de señales de tráfico.</p>

   - <p align="justify"><b>tflite_export.ipynb</b> contiene el proceso de exportación del modelo entrenado para usarlo en Android.</p>

## 🧪 Tecnologías utilizadas 🧪

El proyecto utiliza principalmente:

   - <p align="justify"><b>Python</b>, como lenguaje principal de desarrollo.</p>
   - <p align="justify"><b>Jupyter Notebook</b>, para documentar y ejecutar los procesos de preparación, entrenamiento y exportación.</p>
   - <p align="justify"><b>YOLO / Ultralytics</b>, para la detección de señales de tráfico.</p>
   - <p align="justify"><b>OpenCV</b>, para el tratamiento de imágenes y lectura de dimensiones.</p>
   - <p align="justify"><b>Pillow</b>, para la conversión de imágenes entre formatos.</p>
   - <p align="justify"><b>TensorFlow Lite</b>, para la exportación del modelo a un formato más ligero.</p>

## 🚦 Clases detectadas 🚦

<p align="justify">El modelo está planteado para detectar distintas clases de señales de tráfico, entre ellas límites de velocidad, señales de prohibición, señales de prioridad, señales de peligro y señales de dirección obligatoria.</p>

<p align="justify">Algunas de las clases incluidas son: <b>stop</b>, <b>give way</b>, <b>priority road</b>, <b>speed limit</b>, <b>no entry</b>, <b>pedestrian crossing</b>, <b>roundabout</b>, <b>keep right</b> y <b>restriction ends</b>.</p>

## 🚧 Estado del proyecto 🚧

<p align="justify">Este repositorio recoge el flujo de trabajo de entrenamiento y preparación del modelo. La aplicación de Android se encuentra en el repositorio Angburmun/driving-assistant-app.</p>
