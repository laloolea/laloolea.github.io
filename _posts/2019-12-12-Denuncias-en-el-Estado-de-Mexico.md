---
title:Denuncias en México
tags: [Python,Pandas,Mapbox]
style: fill
color: Blue
description: Proyecto de la materia de Reconocimiento de Patrones en la licenciatura Ciencias de la Computación
external_url: https://blog.usejournal.com/how-to-undo-your-git-failure-b76e31ecac74
---
# Denuncias de victimas en el Estado de México
**Eduardo González Olea, laloolea18@gmail.com**

Este es un proyecto de la materia Reconocimiento de patrones de Ciencias de la computación en la Universidad de Sonora.

En este proyecto usaremos Python cómo nuestro lenguaje de programación, y a su vez utilizaremos las librerias Pandas para tratar los dataframes

Nuestros datos a tratar son de el estado de México los cuales tratan sobre las denuncias en el estado de México, los puedes consultar aquí [Víctimas en carpetas de investigación PGJ](https://datos.cdmx.gob.mx/explore/dataset/denuncias-victimas-pgj/export/?disjunctive.ao)
Descargamos los datos y los guardamos en un dataset, y pudimos ver que tienen la siguiente forma:
<a title="datos feos1" href="https://laloolea.github.io/images/datosfeos1.png">
    <img src="https://laloolea.github.io/images/datosfeos1.png" alt="datos, denuncias">
</a>
<a title="datosfeos3" href="https://laloolea.github.io/images/datosfeos2.png">
    <img src="https://laloolea.github.io/images/datosfeos2.png" alt="datos, denuncias" style="width:887px;height:312px;">
</a>
## Limpieza de datos
Como vimos en las imagenes hay columnas que no nos interesan, y otras que no sirven por lo cual despues de un largo proceso de limpieza de datos borramos todas las columnas innecesarias, quitamos todos los renglones con datos faltantes, e incluso errores de dedo. 
Tambien reagrupamos todas los tipos de denuncias, dado que habia el mismo tipo de delito descrito con diferentes palabras.
Ahora la forma de el dataframe es la siguiente:
<a title="Hermosillo, sonora" href="https://laloolea.github.io/images/datosbonitos.png">
    <img src="https://laloolea.github.io/images/datosbonitos.png" alt="datos, denuncias">
</a>

## Graficas representativas
Ahora si con los datos más limpios, podemos hacer unas graficas representativas como:

<a title="Sexó más común" href="https://laloolea.github.io/images/sexo.png">
    <img src="https://laloolea.github.io/images/sexo.png" alt="sexo, denuncias" style="width:500px;height:500px;">
</a>


<a title="Delitos más comunes" href="https://laloolea.github.io/images/delitos.png">
    <img src="https://laloolea.github.io/images/delitos.png" alt="datos, denuncias" style="width:500px;height:500px;">
</a>


<a title="Edades más comunes" href="https://laloolea.github.io/images/edad.png">
    <img src="https://laloolea.github.io/images/edad.png" alt="edad, denuncias" style="width:500px;height:500px;">
</a>

Despues cómo pudimos ver en nuestro dataset tenemos las columnas longitud y latitud, pudimos graficar punto por punto en un plano, el cual nos da el resultado de la forma de la Ciudad de México:

<a title="Forma" href="https://laloolea.github.io/images/shape.png">
    <img src="https://laloolea.github.io/images/shape.png" alt="ciudad, denuncias">
</a>

## K-Means
Aprovechando estas columnas, podemos aplicar un K-Means que nos agrupe estas ubicaciones.
En el cual usamos el metodo del codito y decidimos hacer 10 centroides
<a title="Metodo del codito" href="https://laloolea.github.io/images/codito.png">
    <img src="https://laloolea.github.io/images/codito.png" alt="codito, denuncias" style="width:500px;height:500px;">
</a>

Hacemos nuestro K-means y ordena las ubicaciones de esta manera
<a title="Metodo del codito" href="https://laloolea.github.io/images/kmeans.png">
    <img src="https://laloolea.github.io/images/kmeans.png" alt="kmeans, denuncias" style="width:500px;height:500px;">
</a>
El cual tiene la misma forma que la figura anterior, pero lo separo en secciones, y con un centroide.
## Interpretación
Usando los centroides generados en el K-means podemos plasmarlos en un mapa real para ubicarlos en la ciudad, el cual tiene la siguiente forma:
<a title="Mapa Cdmx" href="https://laloolea.github.io/images/mapa.png">
    <img src="https://laloolea.github.io/images/mapa.png" alt="mapa, denuncias" >
</a>
En este mapa se puede observar las ubicaciones elegidas por el algoritmo K-Means, cómo el dataset trata de delitos, mi propuesta seria que en cada uno de los centroides, o muy cerca de ellos, se checara si existe una comandancia cercana, y de no ser así, que se construyera una.


No se puede poner el mapa interactivo real , pero si quieren acceder a el pueden verlo en mi libreta del proyecto [Libreta](https://nbviewer.jupyter.org/github/laloolea/pruebas-pandas/blob/master/Denuncias%20victimas%20Estado%20de%20M%C3%A9xico.ipynb)

Tambien quise utilizar algoritmos de aprendizaje supervisado, entonces probe con un Decision Tree Classifier pero ya que los datos en su mayoria son cualitativos no pudo hacerse muy eficiente.
<a title="Decisiontree" href="https://laloolea.github.io/images/decisiontree.png">
    <img src="https://laloolea.github.io/images/decisiontree.png" alt="arbvol, denuncias" >
</a>
Podemos observar en la imagen que la precisión fue demasiado baja para servir como buen indicador.

Intente con un Decision Tree Regressor haciendo una copia de mi dataset pero con variables dummies, pero este no es capaz de representarse de forma gráfica por que esta en variables dummies.
<a title="DecisiontreeRegressor" href="https://laloolea.github.io/images/dummies.png">
    <img src="https://laloolea.github.io/images/dummies.png" alt="arbol, denuncias" >
</a>

## Conclusión
La CdMx es una ciudad muy grande en la cual como se pudo ver en el proyecto, se podia ver que en toda la ciudad hay delitos de diversos tipos, pero con la estrategia propuesta, tal vez se podria tratar de mitigarlos un poco.

Si desean ver más información aquí les dejo el [Repositorio](https://github.com/laloolea/pruebas-pandas) del proyecto
