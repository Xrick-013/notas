# ¿Qué es una API?

Application Programming Interface.

Conjunto de definiciones y protocolos que se utilizan para desarrollar software y permiten la comunicación entre 2 aplicaciones a través de un conjunto de reglas.

<br/>

## Tipos de API

* Simple Object Access Protocol (*SOAP*)
* Remote Procedure Call (*RPC*)
* Representational State Transfer (*REST*)

<br/>

## Características de las API

* Son developer-friendly
* Tratadas como producto
* Diseñadas para consumo
* Estándarizadas
* Tienen su propio Ciclo de Desarrollo de software (*Software Development Life Cycle*)

<br/>

## ¿Qué es REST?

* Arquitectura para sistemas de hipermedios distribuidos.
* Conjunto de restricciones arquitectónicas, no un protocolo ni estándar

<br/>

### ¿Qué es RESTful?

* Client-server
* Stateless
* Cacheable
* Uniform Interface
    + Identificación de recursos
    + Manipulación de recursos a través de representaciones
    + Mensajes auto descriptivos
    + Hipermedia como motor del estado de la apliación
* Layered System
* Code on demand (opcional)

<br/>

### REST v/s RESTful

* **REST**: patrón arquitectónico para crear servicios web
* **RESTful**: implementa los patrones *REST*

<br/>

### Modelo de madurez de Richardson

Desglosa los elementos principales de un enfoque REST de 3 capas para determinar la madurez de un servicio

* URI (recursos)
* HTTP Methods/Verbs
* HATEOAS (hipermedia)

#### Nivel 0 - El pantano de POX

Usa el protocolo de implementación (usualmente HTTP) como un protocolo de comunicación.

#### Nivel 1 - Recursos

Cuando un API puede distinguir entre diferenes recursos se encuentra en el nivel 1. Usa múltiples URIs. Uso un solo método como POST.

#### Nivel 2 - Verbos HTTP

Indica que el API debe usar las propiedades del protocolo para lidiar con la escalabilidad y las fallas.
No usa un único método POST para todas las operaciones.

#### Nivel 3 - Hipermedia

Usa HATEOAS (Hypertext As The Engine Of Application State) para lidiar con el decubrimiento de las posibilidades del API hacia los clientes.

<br/>

## REST API

REST -> Tipo de arquitectura de Software Estandarizado

<br/>

### Beneficios de RESTful Service

<br/>

* Forma de comunicación simple y estándarizado
* Escalable y sin estado
* Alto desempeño y almacenamiento en cache

### Elementos de una REST API

#### Endpoint

Punto de conexión que da servicio a un conjunto de recursos REST

#### Resource

Es un objeto con un tipo, datos asocioados, relaciones con otros recursos y un conjunto de métodos que operan en él.

Similar a una instancia en un lenguaje de programación OOP.

Uso de sustantivos para describir en el URI, preferentemente en plural a menos que el recurso sea claramente un concepto en singular.

Ejemplo:

``` js
    https://empresa.com/api/users
    https://empresa.com/api/getUsers.
```

#### Request

Es el mensaje enviado del cliente al servidor

* Identificar el tipo de acciones a realizar
* Denominación CRUD
* Operaciones HTTP

#### Response

* Información retornada por el servidor
* Los datos típicamente están en formato json
* Códigos de respuesta HTTP

<br/>

## OpenAPI Specification (OAS)

El proyecto **Swagger API** se creó para automatizar la documentación y la generación del SDK de clientes APIs.
Se diseño un formato sencillo para describir la interfaz en *Json* o *YAML* pero lo suficientemente formal para que las máquinas puedan crear Proxys (para el cliente) y Skeletons (para los servidores)
Swagger se convirtió en el estándar de facto. Despues se renombró a **OpenAPI Specification (OAS)**.

<br/>

### Herramientas Swagger

Swagger es un proyecto para el diseño de APIs con la especificación de OpenAPI (OAS).

Framework que permite:
* Modelar APIs con exactitud
* Visualizar durante el diseño
* Estandarizar el estilo de diseño a través de los equipos

<br/>

## Documentación

### Top-Down

Se describe la Rest API en Swagger y a partir de esta se implenta

### Bottom-Up

Se crea la implementación del servicio y se documenta el código para generar la documentación

<br/>

### Se describen

* Recursos
* Endpoints
* Operaciones
* Parametros
* Autenticación

<br/>

### Beneficios

* Formato estandar para describir REST API
    + Puede ser leído por humanos o máquinas
    + Puede ser consumida por DevOps o un proceso automatizado
* Guía
* Extiende la REST API con herramientas
    + API Validator
    + API doc generator
    + SDK generator