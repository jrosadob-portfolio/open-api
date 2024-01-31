# OpenAPI

## Introducción
### Que es un API

### Que es HTTP

### Que es REST

### Códigos de respuesta HTTP

# Que es OpenAPI

# OpenAPI Specification
Puede ver la especificación completa de OpenAPI [aquí](https://swagger.io/specification/v3/)



## API Info
~~~
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
~~~
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
~~~
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
~~~
~~~

### POST Method
~~~
~~~

### PUT Method
~~~
~~~

### PATCH Method
~~~
~~~

### DELETE Method
~~~
~~~

## Data types
~~~
~~~

## Schemas
~~~
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
~~~

~~~

## Security
~~~

~~~

## Status Code
Los códigos de respuesta te ayudan a saber cómo interpretar la respuesta independiente del body de respuesta. Para darle sentido a esas respuestas se han dividido en varios grupos los códigos de respuesta. 

El RFC que se considero para las descripciones siguientes es el [RFC 7231][RFC 7231] por lo que ahí podrán encontrar una explicación más detallada de los usos y limitaciones de cada status.
### Groups
+ `1XX`: Information
+ `2XX`: Success
+ `3XX`: Redirections
+ `4XX`: Client errors
+ `5XX`: Server errors

### Group 1XX: 

### Group 2XX

### Group 3XX

### Group 4XX

### Group 5XX

## Tools

### Online editor
+ [Swagger Online Editor][SwaggerOnLineEditor]  
Features:
  + Generate server: Genera código de servidor basado en la especificación OpenApi.
  + Generate client: Genera cósigo de cliente basado en la especificación OpenApi.

### VSCode extensions
+ OpenAPI (Swagger) Editor [`42crunch.vscode-openapi`][SwaggerEditor]  
Features:
  + Acepta archivo yaml & json
  + Para ver una vista preliminar haga clic en el icono de vista previa arriba a la derecha del vscode.
  + Muestra un icono [API] en el panel izquierdo que nos permite acceder a un treeview de los componentes del api que se está escribiendo y así poder acceder rápidamente a las diferentes secciones.
+ Swagger viewer [`arjun.swagger-viewer`][SwaggerViewer]  
Features:  
  + Acepta archivo yaml & json
  + Para ver una vista preliminar del archivo, haga clic derecho en el archivo y seleccione `Preview Swagger` del menú contextual.
  + Por lo tanto, puedo tener un preview para cada archivo en una pestaña independiente.



<details>
  <summary>Title without markdown</summary>
  Details with markdown, only show at clic on title
</details>


[RFC 7231]: https://datatracker.ietf.org/doc/html/rfc7231#section-6.1
[SwaggerEditor]: https://marketplace.visualstudio.com/items?itemName=42Crunch.vscode-openapi
[SwaggerViewer]: https://marketplace.visualstudio.com/items?itemName=Arjun.swagger-viewer
[SwaggerOnlineEditor]: https://editor.swagger.io/

[Video18]: https://www.udemy.com/course/diseno-apis-openapi/learn/lecture/18639366#overview
