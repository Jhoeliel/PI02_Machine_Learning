# <h1 align=center> **PROYECTO INDIVIDUAL Nº2** </h1>
<p align=center><img src=https://media.datacenterdynamics.com/media/images/GettyImages-844535726.2e16d0ba.fill-1200x630.jpg><p>

Bienvenidos al Proyecto Individual N°2 - Machine Learning, de la etapa de labs de [HENRY](https://www.soyhenry.com/)
<br/>
Elaborado por Jhoeliel Palma Salazar
<hr>

​
## Descripción del problema
​
Hemos sido contactados para el área de Machine Learning de una importante empresa inversora dentro del rubro de la inmobiliaria en Estados Unidos. 
​
El Team Lider le propone dos predicciones posibles, de las cuales puede elegir cuál realizar (o ambas si así lo quiere):
​
1. Implementar un modelo de clasificación con aprendizaje supervisado que permita clasificar el precio de las propiedades en venta, utilizando los datos que se han puesto a su disposición.
​
Para esto debe crear la columna `category_price`, en la cual se consideran las categorías
   * 'low': Para precios entre 0 y 999 dólares.
   * 'medium': Para precios entre 1000 y 1999 dólares.
   * 'high': Para precios desde 2000 dólares en adelante. 
​
    Considerando esta categorización, el objetivo es predecir si una propiedad pertenece a la categoría de precios bajos (low).
​
2. Implementar un modelo de clasificación con aprendizaje no supervisado, utilizando clustering que agrupe las propiedades por segun las **3 categorias** a las que pueden pertenecer. Para ello, solo usaran el dataset de test provisto, eliminando previamente las caracteristicas que presenten nulos.
​
## Métrica a utilizar
​
Como método de evaluación del desempeño, dependerá del modelo que usted decida implementar.
​
1. Para el modelo de aprendizaje supervisado, se utilizará la métrica `Accuracy` para las propiedades de precio bajo (low):
​
$$ Recall=\frac{TP+ TN}{TP+TN+FP+FN}$$
​
Donde $TP$ son los verdaderos positivos, $FP$ los falsos positivos, $FN$ los falsos negativos y $FN$ los falsos negativos. 
​
2. Para el modelo de aprendizaje no supervisado, se utilizará la métrica `Silhouette score`:
​
$$ Silhouette=\frac{b_i-a_i}{max(b_i,a_i)}$$
​
Dónde $b_i$ es la distancia promedio al grupo más cercano desde el punto i, $a_i$ es la distancia promedio a todos los demás puntos del clúster al que pertenece el punto i. 
​
## Archivos provistos
​
Se proveen los siguientes archivos en formato parquet:
 - 'train.parquet': Contiene 346479 registros y 22 dimensiones, el cual incluye la información **numérica** del precio en la columna `price`.
 - 'test.parquet': Contiene 38498 registros y 21 dimensiones, el cual no incluye la información del precio. 

 Link al dataset: https://drive.google.com/drive/folders/1nJ9ZMj6E6zh6McC9NwCA6KopfUIOG_1O
​
## Descripción de las dimensiones
- id: Identificador del anuncio. 
- url: Link web del anuncio.
- region: Región de Estados Unidos en donde se encuentra la propiedad.
- region_url: Link web de los anuncios pertenecientes a la región. 
- price: Precio de la propiedad en petrodólares.
- type: Tipo de propiedad.
- sqfeet: Metros cuadrados de la propiedad.
- beds: Cantidad de dormitorios.
- baths: Cantidad de baños.
- cats_allowed: Si se permiten gatos en la propiedad toma el valor 1, 0 para caso contrario.
- dogs_allowed: Si se permiten perros en la propiedad toma el valor 1, 0 para caso contrario.
- smoking_allowed: Si se permite fumar en la propiedad toma el valor 1, 0 para caso contrario.
- wheelchair_access: Si la propiedad posee acceso para sillas de ruedas toma el valor 1, 0 para caso contrario.
- electric_vehicle_charge: Si la propiedad posee cargador para vehículos eléctricos toma el valor 1, 0 para caso contrario.
- comes_furnished: Si la propiedad viene amueblada toma el valor 1, 0 para caso contrario.
- laundry_options: Opciones de lavandería (w/d in unit: Lavadora/secadora en la propiedad, w/d hookups: conexión para lavadora/secadora, laundry on site: servicio de lavandería en el lugar, laundry in bldg: servicio de lavandería en el edificio, no laundry on sit: sin servicio de lavandería).
- parking_options: Opciones de estacionamiento (off-street parking: zona de estacionamiento, attached garage: garaje incluido, carport: cochera/garaje abierto, detached garage: garaje separado, street parking: estacionamiento delimitado en la calle, no parking: sin estacionamiento, valet parking: estacionamiento con servicio valet).
- image_url: Link web de la imagen de la propiedad en el anuncio. 
- description: Descripción de la propiedad puesta en el anuncio. 
- lat: Latitud.
- long: Longitud.
- state: Código del estado al que pertenece la propiedad.
​
## Sugerencias
- Exploren el dataset. Saquen medidas resumen, vean distribuciones de los datos, analicen bien el tipo de problema, etc.
- Piensen que tipo de modelo podría ser aplicable según la descripción del problema y el tipo de variable de salida.
- Busquen información sobre la métrica aplicada, cada métrica tiene pros y contras.
- Siempre que vean en un dataset coordenadas geoespaciales, es buena estrategia revisar que las mismas correspondan en el mapa al lugar que deberían.
- Si se presentan comentarios, es una buena oportunidad de aplicar procesamiento del lenguaje natural (NLP) para mejorar nuestro modelo.

## Resultados
- Archivo EDA.ipynb el cual contiene el proceso de EDA-ETL que se realizo como parte de la feature engineerging.
