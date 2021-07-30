# Proyecto-Lenguajes-en-WWW---Equipo-11
Proyecto Lenguajes en WWW - Equipo 11

![imagen](https://user-images.githubusercontent.com/50089089/127596038-99a42f04-5d0d-4565-8c90-d797ede2b111.png)

## REACT
* El mantenedor en React consiste de 4 componentes principales. Un index desde donde se instancia el componente principal App, desde el cual se instancian un componente Formulario y un componente Lista.
* El componente formulario guarda datos de encuesta para luego ser guardados por una peticion POST a la API REST. El componente Lista a través de una petición GET a la API obtiene las encuestas existentes para mostrarlas.
* El diagrama de componentes muestra la comunación entre las 3 partes principales del proyecot: Un forntend en React, que se comunica con una API Gateway, la cual utiliza funciones Lambda para manejar las peticiones.


## API
La API consta del recurso __encuesta__ con 2 métodos asociados: get y post. Cada uno de estos posee un endpoint para que el frontend solicite las operaciones correspondientes en relación a los objetos tipo __encuesta__.

## AWS
El componente de AWS hace uso del servicio Lambda para la computación de respuestas y el servicio DynamoDB para el almacenamiento persistente en la nube.

* Cuando un mensaje del tipo _get_ llega desde la API esta instancia la función __getEncuenta__, que se encargará de obtener los datos usando la interfaz __resource__ que provee el sdk de aws para python. Luego se creará un objeto parseable a JSON que se devolverá al componente de la API.
* Cuando un mensaje del tipo _post_ llega desde la API esta instancia la función __postEncuesta__, que se encargará de insertar los datos usando la interfaz __resource__ que provee el sdk de aws para python. Para esto no es necesario crear un objeto especial pues la interfaz  __resource__ trabaja con datos nativos de python. La funcin retorna un mensaje 200 si logró insertar los datos.
