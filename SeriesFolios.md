# Introduction #

Llamadas para el manejo de Series y Folios

## Lista de Series ##

Llamada:

  * _controller_ - folios
  * _view_ - index

Parámetros:

  * Ninguno

Datos POST:

  * Ninguno

## Añadir una Serie ##

Llamada:

  * _controller_ - folios
  * _view_ - add

Parámetros:

  * Ninguno

Datos POST:

  * _`data[Folio][series]`_ - Serie (Obligatorio)
  * _`data[Folio][initial_folio]`_
  * _`data[Folio][default]`_

## Editar una Serie ##

Llamada:

  * _controller_ - folios
  * _view_ - edit

Parámetros:

  * _id_ - ID de la serie a editar

Datos POST:

  * _`data[Folio][series]`_
  * _`data[Folio][initial_folio]`_
  * _`data[Folio][default]`_