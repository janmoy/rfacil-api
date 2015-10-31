# Introduction #

Una organización es aquella entidad que emite Comprobantes Fiscales Digitales.

# Details #

## Lista de organizaciones ##

Llamada:

  * _controller_ - organizations
  * _view_ - index

Parámetros obligatorios:

  * Ninguno

Parámetros opcionales:

  * Ninguno


## Creación ##

> Llamada:

  * _controller_ - organizations
  * _view_ - add

> Parámetros

  * Ninguno

Ejemplo: https://www.rfacil.com/invoices/add.xml?username=username&password=password&apikey=apikey

Datos POST:

  * _`data[Organization][client_type]`_ Tipo de cliente _(Individual,Corporate,Small Business)_
  * _`data[Organization][tax_reference]`_ RFC de la organización
  * _`data[Organization][official_name]`_ Nombre oficial
  * _`data[Organization][name]`_ Nombre de la organización
  * _`data[Organization][field_category]`_ Giro de la organización
  * _`data[Organization][field]`_ Subgiro de la organización

**Relación entre giro y subgiro**

| **Giro** | **Subgiro _(Subgiros separados por 'coma' , enviar solamente uno)_** |
|:---------|:---------------------------------------------------------------------|
| Alimentación y bebidas | Alimentación general,Bebidas,Congelados,Conservas,Perecederos,Varios |
| Construcción e inmobiliaria| Constructoras,Inmobiliarias,Materiales de construcción,Profesionales de la construcción,Varios |
| Hostelería, restauración y cátering | Alojamiento,Otros establecimientos,Restauración Servicios de catering |
| Industria | Automoción,Carbón,Madera,Maquinaria,Metalurgia y minería,Otros sectores,Plásticos y derivados |
| Informática y electrónica | Electrónica y electrodomésticos,Ordenadores y periféricos,Otros productos y servicios,Servicios internet,Software,Telefonía |
| Medios de comunicación | Otros medios de comunicación,Portales Internet,Prensa Publicidad exterior,Radio,Revistas TV |
| Mobiliario y material de oficina | Decoración,Material de oficina,Mobiliario,Papelería,Regalos promocionales,Varios |
| Ocio, cultura y deportes | Agencias de viaje,Arte,Clubs deportivos,Espectáculos,Material deportivo,Música, vídeo y juguetería,Otras actividades |
| Publicidad y artes gráficas | Agencias de publicidad,Diseño gráfico,Fotografía Imprentas,Otros Servicios,Productoras |
| Salud y Belleza | Centros de estética,Medicina y salud,Otros productos y servicios,Perfumería y cosmética |
| Servicios para empresas | Formación,Gestorías y asesorías,Otros servicios para empresas,Trading,Traducción,Transportes,Vending |
| Textil, calzado y complementos | Calzado y complementos,Confección,Joyería,Otros productos,Prendas de vestir,Textil hogar |
| Otros    | _Texto elegido para representar el subgiro de la organización_|

  * _`data[Address][country]`_ País donde se encuentra ubicada la organización
  * _`data[Address][postal_code]`_ Codigo Postal
  * _`data[Address][state]`_ Estado donde se encuentra ubicada la organización
  * _`data[Address][municipality]`_ Municipio
  * _`data[Address][city]`_ Ciudad
  * _`data[Address][quarter]`_ Colonia
  * _`data[Address][street]`_ Calle
  * _`data[Address][exterior_number]`_ Número exterior
  * _`data[Address][interior_number]`_ Número interior
  * _`data[Address][reference]`_ Referencia

  * _`data[Regime][0]`_ Regímenes ficales de la organización _(El número es incremental de dependiendo los regímenes de la organización)_

**Identificadores de los regímenes**
| **id** | Valor del identificador |
|:-------|:------------------------|
| 1      | Régimen de consolidación fiscal |
| 2      | Enajenación de bienes   |
| 3      | Régimen de dividendos para personas físicas |
| 4      | Régimen intermedio para personas físicas |
| 5      | Residentes en el extranjero con fuente de riqueza en México |
| 6      | Arrendamiento uso o goce |
| 7      | Personas morales régimen general de ley |
| 8      | Actividades empresariales y profesionales |
| 9      | Servicios profesionales contabilidad simplificada |
| 10     | Régimen de intereses para personas físicas |
| 11     | Actividades empresariales contabilidad simplificada |
| 12     | Personas morales con fines no lucrativos |
| 13     | Personas morales del régimen simplificado |
| 14     | Personas morales de sociedades cooperativas de producción |

**Ejemplo:**
_`data[Regime][0] => 1`_,
_`data[Regime][1] => 4`_,
_`data[Regime][2] => 5`_

  * _`data[Entity][type]`_ Tipo de entidad a dar de alta,  _Opciones: (Organization)_