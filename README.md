DESAFIOS

UNO: Vectorización de texto y modelo de clasificación Naïve Bayes

* Tenemos un set de datos con temas de distintas categorias
* Se usa cosine_similarity, para validar clasificacion del texto en funcion de su categoria
* En general, la clasificacion se ve funciona bien.
* Se busca entrenar el mejor modelo, para ello se usa una busqueda bayesiana de los mejores hiperparametros, classifier y  vectorizer . Esta busqueda no garantiza sean los mejores en todos los sentidos, si no, los mejores en esa esploracion
* Se invierte matriz de documento-término para hallar las palabras relacionadas a una dada, en general da resultados coherentes


