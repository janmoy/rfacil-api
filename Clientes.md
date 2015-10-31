# Introduction #

Llamadas para manejo de clientes


# Details #

## Lista de clientes ##

Llamada:

  * _controller_ - clients
  * _view_ - index

Parámetros obligatorios:

  * Ninguno

Parámetros opcionales:

  * _search_ - Palabra de búsqueda (en RFC o Razón Social)

## Añadir un cliente ##

Llamada:

  * _controller_ - clients
  * _view_ - add

Parámetros:

  * Ninguno

Datos POST:

  * _`data[Client][official_name]`_ - Razón Social (Obligatorio)
  * _`data[Client][tax_reference]`_ - RFC del cliente (Obligatorio, en mayúsculas, únicamente caracteres alfanuméricos, y 12 a 13 caracteres)
  * _`data[Client][email]`_
  * _`data[Client][phone]`_
  * _`data[Client][street]`_
  * _`data[Client][exterior_number]`_
  * _`data[Client][interior_number]`_
  * _`data[Client][postal_code]`_
  * _`data[Client][state]`_
  * _`data[Client][quarter]`_
  * _`data[Client][municipality]`_
  * _`data[Client][city]`_
  * _`data[Client][country]`_ - Valor por defecto: México

_**Ejemplo ( JavaScript )**_
```
var data = {
            "data[Client][official_name]" : "Prueba" ,
            "data[Client][tax_reference]" : "AAA010101AAA" ,
            "data[Client][email]" : "prueba@rfacil.com" ,
            "data[Client][phone]" : "111111111" ,
            "data[Client][street]" : "Calle" ,
            "data[Client][exterior_number]" : "103" ,
            "data[Client][interior_number]" : "C" ,
            "data[Client][postal_code]" : "1111" ,
            "data[Client][state]" : "México" ,
            "data[Client][quarter]" : "Colonia" ,
            "data[Client][municipality]" : "Municipio" ,
            "data[Client][city]" : "Ciudad" ,
            "data[Client][country]" : "" ,
           };
$.post('http://CFDI_URL/clients/add.xml?username=USERNAME&password=PASSWORD@&apikey=APIKEY&tax_reference=AAA010101AAA', data);
```

## Editar un cliente ##

Llamada:

  * _controller_ - clients
  * _view_ - edit

Parámetros:

  * _id_ - ID del cliente a editar

Datos POST:

  * _`data[Client][id]`_ - ID del cliente (Obligatorio)
  * _`data[Client][official_name]`_ - Razón Social (Obligatorio)
  * _`data[Client][tax_reference]`_ - RFC del cliente (Obligatorio, en mayúsculas, únicamente caracteres alfanuméricos, y 12 a 13 caracteres)
  * _`data[Client][email]`_
  * _`data[Client][phone]`_
  * _`data[Client][street]`_
  * _`data[Client][exterior_number]`_
  * _`data[Client][interior_number]`_
  * _`data[Client][postal_code]`_
  * _`data[Client][state]`_
  * _`data[Client][quarter]`_
  * _`data[Client][municipality]`_
  * _`data[Client][city]`_
  * _`data[Client][country]`_ - Valor por defecto: México

## Borrar un cliente ##

Llamada:

  * _controller_ - clients
  * _view_ - delete

Parámetros:

  * _id_ - ID del cliente a borrar

## Busqueda de un cliente por RFC ##

Llamada:

  * _controller_ - clients
  * _view_ - view\_by\_tax\_reference

Parámetros:

  * _tax\_reference_ - RFC del cliente a buscar

## Detalle de un cliente ##

Llamada:

  * _controller_ - clients
  * _view_ - view
Parámetros:

  * _id_ - ID del cliente

## Detalle de un cliente por RFC ##

Llamada:

  * _controller_ - clients
  * _view_ - view\_by\_tax\_reference

Parámetros:

  * _tax reference_ - RFC del cliente