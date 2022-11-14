# Unidad 2

## Representación externa de datos

* La información almacenada en un programa es representada como estructuras de datos
* Los datos deben ser convertidos a una secuencia de bytes antes de ser envíados. Al momento de su recepción deben ser reconstruidos
* No todos los sistemas representan los valores primitivos de la misma forma.
* Se usan 2 métodos para habiliar la comunicación entre 2 nodos cualesquiera
    + Antes de la transmición se convierten los datos a un formato externo y en la recepción en la forma local.
    RMI Y RPC
    + Los datos se envían en la forma del emisor, con la información del formato para que el receptor pueda convertirlos e interpretarlos.
* **Marshalling**: convertir los datos a una forma adecuada para la transmición del mensaje
* **Unmarshalling**: desensamblar los datos y convertirlos a datos equivalentes en el receptor
* **RMI**: el mensaje es serializado antes del envío y des-serializado al momento de la recepción.
* **XML** (eXtensible Markup Language): define un formato textual para la representación externa de los datos. Formato para transmitir mensajes entre servicios web.
* **JSON** (JavaScript Object Notation): representación ligera de transmición de datos.
* **Protocol buffers**: mécanismo de Google para serialización de datos estructurados.

<br/>

## XML

* Definido por la World Wide Web Consortium para uso general en la Web
* Deriva del **SGML** (Standarized Generalized Markup Language)
* Define estructuras de datos en la Web
* Usos:
    + Habilitar la comunicación entre los servicios web y clientes
    + Definir las interfaces de los servicios web
    + Definir las propiedades de los servicios web
* Permite definir etiquetas propias
* Debe ser autodescriptivo
* Uso de tags y namespaces
* Human-readable

<br/>

### Documento XML

* Prolog: ubicado en la primera linea. Como mínimo debe contener la versión de XML y encoding.
* Element: porciones de datos
* Attribute: par nombre-valor asociado al elemento
* CDATA: forma de representar los datos.
* XML namespaces: conjunto de nombres para la colección de tipos de elentos y atributos referenciados por una URL.
* Esquemas (xsd): estructura de un documento XML
* Web Service Definition Language (WSDL): describir servicios

<br/>

## Protocolos Request-reply

* Soporta roles cliente-servidor
* Generalmente la comunicación es síncroma, el cliente se bloquea hasta recibir respuesta del servidor
* Se basa en 3 primitivas de comunicación:
    + doOperation
    + getRequest
    + sendReply

| Client      | | Server |
| ------      | - | ----- |
|             | Request| |
| doOperation | -------> | getRequest |
|             | Message | |
| (wait)      | | Select Operation <br> Execute Operation |
|             | Reply     | |
|             | <------- | sendReply |
|             | Message | |
| (Continuation) | | |