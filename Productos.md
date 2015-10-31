# Introduction #

Llamadas para manejo de productos


# Details #

## Lista de productos ##

Llamada:

  * _controller_ - products
  * _view_ - index

Parámetros obligatorios:

  * Ninguno

Parámetros ocionales:

  * _search_ - Palabra de búsqueda (en RFC o Razón Social)

## Añadir un producto ##

Llamada:

  * _controller_ - products
  * _view_ - add

Parámetros:

  * Ninguno

Datos POST:

  * _`data[Product][title]`_ - Nombre (Obligatorio)
  * _`data[Product][code]`_
  * _`data[Product][manufacturer]`_
  * _`data[Product][description]`_
  * _`data[Product][quantity_per_unit]`_
  * _`data[Product][unit_price]`_
  * _`data[Product][weight]`_
  * _`data[Product][pack_size]`_
  * _`data[Product][sku]`_
  * _`data[Product][serial_number]`_
  * _`data[Product][lot]`_

_**Ejemplo ( JavaScript )**_
```
var data = {
            "data[Product][title]":"prueba",
            "data[Product][code]":"prueba",
            "data[Product][unit_price]": 451.25
           };
$.post('http://CFDI_URL/products/add.xml?username=USERNAME&password=PASSWORD@&apikey=APIKEY&tax_reference=AAA010101AAA', data);
```

## Editar un producto ##

Llamada:

  * _controller_ - products
  * _view_ - edit

Datos POST:

  * _`data[Product][id]`_ - ID del producto (Obligatorio)
  * _`data[Product][title]`_ - Nombre (Obligatorio)
  * _`data[Product][code]`_
  * _`data[Product][manufacturer]`_
  * _`data[Product][description]`_
  * _`data[Product][quantity_per_unit]`_
  * _`data[Product][unit_price]`_
  * _`data[Product][weight]`_
  * _`data[Product][pack_size]`_
  * _`data[Product][sku]`_
  * _`data[Product][serial_number]`_
  * _`data[Product][lot]`_

_**Ejemplo ( JavaScript )**_
```
var data = {
            "data[Product][id]": 1,
            "data[Product][title]":"prueba",
            "data[Product][code]":"prueba",
            "data[Product][unit_price]": 451.25
           };
$.post('http://CFDI_URL/products/edit.xml?username=USERNAME&password=PASSWORD@&apikey=APIKEY&tax_reference=AAA010101AAA', data);
```


## Borrar un producto ##

Llamada:

  * _controller_ - products
  * _view_ - delete

Parámetros:

  * _id_ - ID del producto a borrar

## Detalle de un producto ##

Llamada:

  * _controller_ - products
  * _view_ - view
Parámetros:

  * _id_ - ID del producto a ver