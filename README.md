DESAFIOS


UNO: Vectorización de texto y modelo de clasificación Naïve Bayes

* Tenemos un set de datos con temas de distintas categorias
* Se usa cosine_similarity, para validar clasificacion del texto en funcion de su categoria
* En general, la clasificacion se ve funciona bien.
* Se busca entrenar el mejor modelo, para ello se usa una busqueda bayesiana de los mejores hiperparametros, classifier y  vectorizer . Esta busqueda no garantiza sean los mejores en todos los sentidos, si no, los mejores en esa esploracion
* Se invierte matriz de documento-término para hallar las palabras relacionadas a una dada, en general da resultados coherentes

DOS: Similitud
* Utilizaremos como dataset canciones de bandas de habla inglesa
* Preprocesamiento: Aceptar solo string validos
* Se usa Word2Vec, la eleccion de paramtros como window y sg surgio por la experimentacion. Un window de 4 al ser la mitad sobre la media de longitud de palabras y sg=0 al mostrar similares resultados pero en menor tiempo
* En el entrenamiento, la cantidad de epocas si bien se pudo extender no mostro mejora mas alla de 20. Se vio era suficiente
* El resultado del modelo es mixto, casos donde las palabras si tienen sentido y otros donde no es al menos tan claro

TRES: Prediccion de proxima palabra
* Dataset: https://raw.githubusercontent.com/cristianEmel/nlp/main/cyberbullying_tweets.csv
* Modelo:
* ![image](https://github.com/user-attachments/assets/8dc3c350-e77e-446c-9e4f-22ab2085082a)
* Si bien el modelo genera texto, el mismo no parece ser muy coherente y cae en repeticiones, al texto: "I couldn't give two fuck on what niggers think still", tenemos: "I couldn't give two fuck on what niggers think still the the the the the"

CUATRO: Sistema pegunta/respuesta
* Dataset: https://raw.githubusercontent.com/cristianEmel/nlp/refs/heads/main/Conversation.csv
* Preprocesamiento: Eliminacion de caracteres especiales, agregado de caracteres marcadores <sos> y <eos> de inicio y fin
* Se hace uso de embeddings para el entrenamiento, en este caso de FasttextEmbeddings
* Modelo: ![image](https://github.com/user-attachments/assets/822df30b-8be1-47b8-bcb4-a9edf04ba13b)
* Entrenamiento: No se vio el proceso de entrenamiento mejorar entre epocas, se probo ajustando hiperparametros como las epocas, lr etc, no se vio mejora ![image](https://github.com/user-attachments/assets/72b4375d-fea8-4fb7-9664-f5bcac321eba)
* En el primero intento de probar el modelo para ver sus inferencias, se vio solia caer en ciclo de repetir las palabras : i you
* En el segundo intendo de probar el modelo para ver sus inferencias, cambiando la funcion de seleccion por una binomial, si bien varia las palabras, las mismas no parecen tener coherencia o sentido


