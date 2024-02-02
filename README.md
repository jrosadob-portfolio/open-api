# OpenAPI

## Introducción
### Que es un API

### Que es HTTP

### Que es REST

### Códigos de respuesta HTTP
Los códigos de respuesta te ayudan a saber cómo interpretar la respuesta independiente del body de respuesta. Para darle sentido a esas respuestas se han dividido en varios grupos los códigos de respuesta. 

El RFC que se considero para las descripciones siguientes es el [RFC 7231][RFC 7231] por lo que ahí podrán encontrar una explicación más detallada de los usos y limitaciones de cada status.
### Groups
<details>
  <summary>Group 1XX: Information</summary>
  
  + `Pendiente:` Lorem ipsum.
  + `Pendiente:` Lorem ipsum.
</details>

<details>
  <summary>Group 2XX: Success</summary>
  
  + `200 Ok`  
  Respuesta más común y usada. Significa que la petición ha sido atendida exitosamente. Debería tener siempre un body de respuesta, ya que si no lo tiene sería mejor usar un 204. 
  +	`201 Created`  
  Se ha creado un nuevo recurso exitosamente. Este nuevo recurso es accesible en el API. La respuesta debe tener un header Location esto es obligatorio porque el header contiene la URI del recurso creado, así el consumidor sabe donde puede encontrar ese nuevo recurso. El body de respuesta puede contener o no el recurso creado.
  + `202 Accepted`  
  La respuesta ha sido aceptada para procesarla, pero aún no se termina. Esto puede ser porque es una operación en segundo plano o asíncrona de cierta forma. Puede o no tener un body de respuesta que indique un resumen o la forma de dar seguimiento a esa tarea asíncrona. También se debe usar un Header Content-Location con la URL de donde puedes ver el status de la petición. 
  + `204 No content`  
  La petición fue ejecutada exitosamente pero no tiene un body de respuesta porque no es necesario a comparación de del resto de códigos. Si se requiriera proveer más información se puede hacer uso de headers.
</details>

<details>
  <summary>Group 3XX: Redirections</summary>

  + `301 Moved Permanently`  
  Te dice que el recurso se ha movido permanentemente a otra dirección. Podrías usar el header Location para indicar cuál es esa URI nueva del recurso. Puede ser útil si estamos migrando algún recurso a otro endpoint o algún otro recurso como un documento o reporte. 
  + `303 See Other`  
  El servidor redirige al cliente a otra URI. Aquí hay que usar el header Location para poder tener la URI del recurso a consultar. Este código comúnmente se usa para operaciones en bulk, operaciones masivas, operaciones asíncronas porque proveen una URI donde consultar el resultado.
  + `304 Not modified`  
  En este status el cliente solicita un recurso (GET o HEAD) que no ha sido modificado desde que se consultó la última vez. Entonces no es necesario regresar ese mismo recurso en el payload de respuesta. Para esos casos debes usar 304 y se puede proveer otra información por medio de headers. Un uso común de esto son por ejemplo el caché donde se usan headers como Cache-Control, Content-Location, Date, ETag y se podría responder con el recurso que no tiene cambio.
</details>

<details>
  <summary>Group 4XX: Client errors</summary>
  
  + `400 Bad Request`
  Aquí el cliente no debe de hacer de nuevo la petición sin cambiarla ya que está mal formada. Este error puede ser visto como un error por default cuando el resto de errores no aplica. También es comúnmente usado para errores funcionales por ejemplo campos requeridos, fechas fuera de rango, monto máximo. Situaciones que el cliente puede corregir. 
  + `401 Unauthorized`  
  La aplicación o el usuario autenticado no tiene autorización para acceder al recurso. También puede ser que esté formando mal el token de seguridad. 
  + `403 Forbidden`  
  La aplicación o el usuario autenticado a pesar de que tiene autorización al recurso, no tiene suficientes privilegios para el recurso.
  + `404 Not found`  
  Significa que se ha logrado una conexión pero no se encontró el recurso solicitado.
  + `405 Method not allowed`  
  El recurso existe pero no el método http que se intenta aplicar no está permitido. 
  + `409 Conflict`  
  La petición no pudo completarse debido a un conflicto o no puedo generar el estatus del recurso. Aquí es necesario resolver el conflicto antes de intentar de nuevo la petición. Este código de error no puede ser usado para errores funcionales o de negocio como en el caso del 400. 
</details>

<details>
  <summary>Group 5XX: Server errors</summary>
  
  + `500 Internal Server Error`  
  Es un error del servidor, este es el error por default, normalmente desconocido.
  + `501 Not implemented`  
  El servicio está definido pero no está implementado. Quiere decir que puede ser accesible pero no esta funcionando al 100%.
  + `502 Bad gateway`  
  Significa que hay un servidor que es inaccesible o no está correctamente configurado el gateway.
  + `503 Service unavailable`  
  El servidor no puede hacer que el servicio esté disponible.
  + `504 Gateway timeout`
  Existe un error por un tercero en el tiempo de atención a la petición.
</details>

# Que es OpenAPI

# OpenAPI Specification
Puede ver la especificación completa de OpenAPI [aquí](https://swagger.io/specification/v3/)

## API Info
~~~yml
openapi: 3.0.3
info:
  title: SpaceShips
  description: 
  contact:
    name: Javier
    email: jrosadob@hotmail.com
  version: 1.0.0

~~~

## Servidores
~~~yml
servers:
  - url: https://dev.spaceships.com/v1
    description: Development environment  
  - url: https://qa.spaceships.com/v1
    description: Qa environment
  - url: https://spaceships.com/v1
    description: Production environment
~~~

## Endpoint tags
Agrupan en una sección nuestros endpoint.
El orden de los tags determinan el orden en el que se muestran las diferentes secciones (tags)
~~~yml
tags:
  - name: SpaceShips1
    description: Vehicle to travel through SpaceShips
    externalDocs:
      description: Find more
      url: http://info.spaceship.com
  - name: SpaceShips2
    description: Vehicle to travel through SpaceShips2
~~~

## Object paths (Endpoints)
### GET Method
~~~yml
~~~

### POST Method
~~~yml
~~~

### PUT Method
~~~yml
~~~

### PATCH Method
~~~yml
~~~

### DELETE Method
~~~yml
~~~

## Data types
~~~yml
~~~

## Schemas
~~~yml
~~~


## Model compositions (Inheritance and Polymorphism)
Muestra una forma de enviar datos de un Cat/Dog al servicio
Donde uno puede seleccionar el dato de ejemplo: Cat/Dog
Y según eso referirse a un shcema de datos Cat/Dog
No lo usado y no lo veo uso pero ahi está.  
Usa oneOf y allOf.  
Ver en:  
[18.Composición de modelos (Inheritances and Polymorphism)][Video18]
~~~
~~~

## Enums
~~~yml

~~~

## Security
~~~yml

~~~

## Tools
### Online editor
+ [Swagger Online Editor][SwaggerOnLineEditor]  
  <details>
    <summary>See features:</summary>  
    
    + `Generate server:` Genera código de servidor basado en la especificación OpenApi.
    + `Generate client:` Genera cósigo de cliente basado en la especificación OpenApi.
  </details>

### VSCode extensions
+ OpenAPI (Swagger) Editor [`42crunch.vscode-openapi`][SwaggerEditor]  
  <details>
    <summary>See features:</summary>  
    
    + Acepta archivo yaml & json
    + Para ver una vista preliminar haga clic en el icono de vista previa arriba a la derecha del vscode.
    + Muestra un icono [API] en el panel izquierdo que nos permite acceder a un treeview de los componentes del api que se está escribiendo y así poder acceder rápidamente a las diferentes secciones.  
  </details>

+ Swagger viewer [`arjun.swagger-viewer`][SwaggerViewer]  
  <details>
    <summary>See features:</summary>
  
    + Acepta archivo yaml & json  
    + Para ver una vista preliminar haga clic en el icono de vista previa arriba a la derecha del vscode.  
    + Muestra un icono [API] en el panel izquierdo que nos permite acceder a un treeview de los componentes del api que se está escribiendo y así poder acceder rápidamente a las diferentes secciones.
  </details>

[RFC 7231]: https://datatracker.ietf.org/doc/html/rfc7231#section-6.1
[SwaggerEditor]: https://marketplace.visualstudio.com/items?itemName=42Crunch.vscode-openapi
[SwaggerViewer]: https://marketplace.visualstudio.com/items?itemName=Arjun.swagger-viewer
[SwaggerOnlineEditor]: https://editor.swagger.io/

[Video18]: https://www.udemy.com/course/diseno-apis-openapi/learn/lecture/18639366#overview
