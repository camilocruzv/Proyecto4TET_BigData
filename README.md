# Proyecto4 - Big Data
Analítica de texto para procesamiento de noticias

## Integrantes

- Cristian Villamizar Ochoa - cvillam8@eafit.edu.co
- Camilo Cruz Villegas - ccruzvi@eafit.edu.co

## Diseño

La metodología de diseño para este proyecto fue CRISP-DM. A continuación sus diferentes fases:

## 1. Business Understanding

**Contexto:**

La minería o analítica de texto, son un conjunto de modelos, técnicas, algoritmos y
tecnologías que permiten procesar texto de naturaleza NO ESTRUCTURADA.
La minería de texto (text mining) permite transformar el texto en una forma
estructurada, de tal forma que facilite una serie de aplicaciones como Búsqueda en
texto, relevancia de documentos, entendimiento natural del lenguaje (NLP), traducción
automática entre idiomas, análisis de sentimientos, detección de tópicos entre muchas
otras aplicaciones.
Quizás el procesamiento más sencillo de todos sea el wordcount, el cual consiste en
determinar la frecuencia de la palabra por documento o por todo el dataset.

**Problema:**

Se tiene un conjunto de noticias en texto libre, sobre el cual se desea realizar:

PRIMERA PARTE: PREPARACIÓN DE DATOS
LAS NOTICIAS DEBEN SER PRE-PROCESADAS PARA PREPARAR LOS DATOS PARA LA
ANALITICA, DENTRO DE LAS SUGERENCIAS DE PREPARACIÓN ESTÁN:
1. Remover caracteres especiales (. , % ( ) ‘ “ ….
2. Remover stop-words
3. Remover palabras de longitud 1
4. Stemming / lemmatization

SEGUNDA PARTE: explorar al menos una técnica de analítica de texto NLP de los
diferentes modelos y aplicaciones de SparkML-NLP, deberá ser creativos para encontrar
dicha navegación, entre las opciones:
• Agrupamiento de textos (algoritmos como k-means)
• Detección de comunidades (algoritmos como Louvain)
• Detección de tópicos y Clasificación de Textos (LDA, Word2vec, Doc2Vec)
• Análisis de sentimientos
• Generación automáticas de keyworks
• Ranking de documentos para búsqueda y recuperación
• Etc.

## 2. Data Understanding

Cargamos los datasets, los cuales se encuentran almacenados en el DBFS de DataBricks:

[Upload Datasets](https://user-images.githubusercontent.com/38144641/69304553-0c51d400-0bef-11ea-85d7-623782843df8.JPG)

Análizamos los datos, y mostramos el resultado de transformar archivos de entrada en un DataFrame, analizamos sus columnas y sus valores.


[Show Columns](https://user-images.githubusercontent.com/38144641/69305036-a8c8a600-0bf0-11ea-88a0-57e78eb8e003.JPG)

[Show Dataframe](https://user-images.githubusercontent.com/38144641/69305039-a8c8a600-0bf0-11ea-8dea-52118c689abb.JPG)

Posterior a esto verificamos que los datos son consistentes y realmente aportan a la solución del problema.

## 2. Data Preparation

Tokenizamos su la columna *content* para realizar una correcta transformación del dataset de csv a dataframe, y además de esto removemos caracteres especiales y palabras de longitud 1:

[Tokenization](https://user-images.githubusercontent.com/38144641/69305042-aa926980-0bf0-11ea-9d85-70413cfec46f.JPG)

Los valores tokenizados se mostrarán en una columna nueva llamada *tokens*:

[Show result](https://user-images.githubusercontent.com/38144641/69305043-ab2b0000-0bf0-11ea-8051-2f20170d0747.JPG)

Utilizando la librería pyspark.ml.feature, removemos los stopwords del inglés:

[Remove StopWords](https://user-images.githubusercontent.com/38144641/69305045-ac5c2d00-0bf0-11ea-8cb9-ff4378e0eb15.JPG)

Se muestran el resultado en una nueva columna llamada *filtered*:

[Show Results](https://user-images.githubusercontent.com/38144641/69305048-acf4c380-0bf0-11ea-8c90-d9f1160867f4.JPG)

## 3. Modeling

Utilizamos la función CountVectorizer para contar el número de veces que aparecen cada una de las palabras que se encuentran el dataframe tokenizado:

[Vectorization](https://user-images.githubusercontent.com/38144641/69305049-acf4c380-0bf0-11ea-97b7-d0680a8e6aa0.JPG)

Como resultado, podemos observar las palabras más utilizadas en el archivo cargado:

[Show count vectorizer](https://user-images.githubusercontent.com/38144641/69305050-ad8d5a00-0bf0-11ea-9a53-93881c717b05.JPG)

De igual forma, se utilizan otras técnicas de análitica de datos como TF-IDF:

[TF_IDF](https://user-images.githubusercontent.com/38144641/69305051-ae25f080-0bf0-11ea-991e-8110d7eaeaa3.JPG)

[TF_IDF2](https://user-images.githubusercontent.com/38144641/69305052-ae25f080-0bf0-11ea-94b6-4f0e3490bfe0.JPG)

[TF_IDF3](https://user-images.githubusercontent.com/38144641/69305055-aebe8700-0bf0-11ea-9767-f7e71726628c.JPG)

[TF_IDF4](https://user-images.githubusercontent.com/38144641/69305031-a7977900-0bf0-11ea-955a-497002c7140e.JPG)

## 3. Evaluation y Deployment

**DATABRICKS**

En el siguiente link se puede encontrar la solución del problema: 
https://community.cloud.databricks.com/?o=8391199092082772#notebook/1358279811746325/command/1358279811746342


