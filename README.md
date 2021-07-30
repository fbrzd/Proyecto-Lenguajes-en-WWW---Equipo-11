# Proyecto-Lenguajes-en-WWW---Equipo-11
Proyecto Lenguajes en WWW - Equipo 11

![imagen](https://user-images.githubusercontent.com/50089089/127596038-99a42f04-5d0d-4565-8c90-d797ede2b111.png)

## API
La API consta del recurso __encuesta__ con 2 métodos asociados: get y post. Cada uno de estos posee un endpoint para que el frontend solicite las operaciones correspondientes en relación a los objetos tipo __encuesta__.

## AWS
El componente de AWS hace uso del servicio Lambda para la computación de respuestas y el servicio DynamoDB para el almacenamiento persistente en la nube.

* Cuando un mensaje del tipo _get_ llega desde la API esta instancia la función __getEncuenta__, que se encargará de obtener los datos usando la interfaz __resource__ que provee el sdk de aws para python. Luego se creará un objeto parseable a JSON que se devolverá al componente de la API.
* Cuando un mensaje del tipo _post_ llega desde la API esta instancia la función __postEncuesta__, que se encargará de insertar los datos usando la interfaz __resource__ que provee el sdk de aws para python. Para esto no es necesario crear un objeto especial pues la interfaz  __resource__ trabaja con datos nativos de python. La funcin retorna un mensaje 200 si logró insertar los datos.
