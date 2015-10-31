# Introduction #

Llamadas para manejo de CFDI's


# Details #

## Lista de CFDI's ##

Llamada:

  * _controller_ - invoices
  * _view_ - index

Parámetros

  * _search\_param_ - Patrón de búsqueda por RFC o Razón Social **(Opcional)**

Ejemplo:
  * https://www.rfacil.com/invoices/index/AAAA010101AAA.xml?username=username&password=password&apikey=apikey


## Detalle de Factura ##

Llamada:

  * _controller_ - invoices
  * _view_ - detail

Parámetros

  * _id_ - id de la factura


Ejemplo: https://www.rfacil.com/invoices/view/58.xml?username=username&password=password&apikey=apikey

## Creación ##

Llamada:

  * _controller_ - invoices
  * _view_ - add

Parámetros

  * Ninguno

Ejemplo: https://www.rfacil.com/invoices/add.xml?username=username&password=password&apikey=apikey

Datos POST:

  * _`data[Invoice][total]`_  Total
  * _`data[Invoice][discount_amount]`_  Monto de descuento
  * _`data[Invoice][discount_percent]`_  Porcentaje de descuento, opcional
  * _`data[Invoice][discount_reason]`_  Motivo de descuento, opcional
  * _`data[Invoice][subtotal]`_  Subtotal
  * _`data[Invoice][subject]`_  Asunto
  * _`data[Invoice][payment_method]`_  Método de pago
|**Cuenta de pago** |  **Método de pago** |
|:------------------|:--------------------|
| No                | No identificado     |
| Si                | Check               |
| Si                | Credit Card         |
| No                | PayPal              |
| No                | Exchange            |
| Si                | Transfer            |
| No                | Deposit             |
| No                | Cash                |
| No                | Other               |

  * _`data[Invoice][payment_account]`_  Cuenta de pago **(Solo si el método de pago lo requiere)**
  * _`data[Invoice][payment_form]`_  Forma de pago **(Por default es: Pago en una sola exhibición)**
  * _`data[Invoice][currency]`_  Moneda **(1=Peso, 2=Dolar)**
  * _`data[Invoice][exchange_rate]`_  Cambio _**(Requerido solo si se factura en dolares)**_
  * _`data[Invoice][type]`_  Tipo de comprobante (_Ingreso_,_Egreso_)
  * _`data[Invoice][client_id]`_  Id del cliente a facturar
  * _`data[Invoice][tax_type]`_  Tipo de impuesto del documento (_INDIVIDUAL_,_GROUP_)
> o

  * _`data[Client][create_client]`_  true para crear un nuevo cliente
  * _`data[Client][tax_reference]`_  RFC
  * _`data[Client][official_name]`_  Razón Social
  * _`data[Client][email]`_
  * _`data[Client][phone]`_
  * _`data[Client][postal_code]`_
  * _`data[Client][state]`_
  * _`data[Client][municipality]`_
  * _`data[Client][city]`_
  * _`data[Client][quarter]`_
  * _`data[Client][street]`_
  * _`data[Client][country]`_
  * _`data[Client][exterior_number]`_
  * _`data[Client][interior_number]`_

Productos a facturar. Se puede crear un nuevo producto, indicando su nombre, o bien, usar uno existente, indicando su id

  * _`data[InvoicesProduct][0][title]`_  Nombre del producto
  * _`data[InvoicesProduct][0][code]`_  Código de Producto (opcional)
  * _`data[InvoicesProduct][0][description]`_ Descripción (opcional)
  * _`data[InvoicesProduct][0][price]`_  Precio unitario
  * _`data[InvoicesProduct][0][quantity]`_  Cantidad
  * _`data[InvoicesProduct][0][Tax][0][id]`_  id del impuesto, de acuerdo al API correspondiente (1)
  * _`data[InvoicesProduct][0][Tax][0][percentage]`_  porcentaje del impuesto (16)
  * _`data[InvoicesProduct][0][Tax][0][label]`_  etiqueta del impuesto (IVA)
  * _`data[InvoicesProduct][0][Tax][0][name]`_  nombre del impuesto (IVA Traslado)
  * _`data[InvoicesProduct][0][Tax][0][amount]`_  cantidad del impuesto para este producto

  * _`data[InvoicesProduct][1][title]`_  Nombre del producto
  * _`data[InvoicesProduct][1][code]`_  Código de Producto (opcional)
  * _`data[InvoicesProduct][1][description]`_ Descripción (opcional)
  * _`data[InvoicesProduct][1][price]`_  Precio unitario
  * _`data[InvoicesProduct][1][quantity]`_  Cantidad

  * _`data[InvoicesProduct][1][Tax][0][id]`_  id del impuesto
  * _`data[InvoicesProduct][1][Tax][0][percentage]`_  porcentaje del impuesto (16)
  * _`data[InvoicesProduct][1][Tax][0][amount]`_  cantidad del impuesto para este producto

  * _`data[InvoicesProduct][1][Tax][1][id]`_  id del siguiente impuesto
  * _`data[InvoicesProduct][1][Tax][1][percentage]`_  porcentaje del impuesto
  * _`data[InvoicesProduct][1][Tax][1][amount]`_  cantidad del impuesto para este producto


  * _`data[InvoicesProduct][2][id]`_  Id del producto
  * _`data[InvoicesProduct][2][quantity]`_  Cantidad
  * _`data[InvoicesProduct][2][price]`_  Precio Unitario
  * _`data[InvoicesProduct][2][Tax][0][id]`_  id del impuesto (1)
  * _`data[InvoicesProduct][2][Tax][0][percentage]`_  porcentaje del impuesto (16)
  * _`data[InvoicesProduct][2][Tax][0][amount]`_  cantidad del impuesto para este producto

etc...


**COMPLEMENTOS _(OPCIONAL)_**

> _**COMPLEMENTOS POR CONCEPTO**_

> _**Instituciones Educativas privadas**_

  * _`data[InvoicesProduct][0][Complements][INSTEDUPRIV][ComplementInstedupriv][nombre_alumno]`_  Nombre del alumno
  * _`data[InvoicesProduct][0][Complements][INSTEDUPRIV][ComplementInstedupriv][curp]`_  CURP del alumno
  * _`data[InvoicesProduct][0][Complements][INSTEDUPRIV][ComplementInstedupriv][nivel_educativo]`_  Nivel educativo
  * _`data[InvoicesProduct][0][Complements][INSTEDUPRIV][ComplementInstedupriv][aut_rvoe]`_  Clave del centro de trabajo
  * _`data[InvoicesProduct][0][Complements][INSTEDUPRIV][ComplementInstedupriv][rfc_pago]`_  RFC de quien realiza el pago cuando sea diferente a quien recibe el servicio **(Opcional)**


> _**ELEMENTOS POR CONCEPTO**_

> _**Información aduanera**_
  * _`data[InvoicesProduct][0][ElementConcept][INFOADUANERA][1][numero]`_ Número de la aduana
  * _`data[InvoicesProduct][0][ElementConcept][INFOADUANERA][1][aduana]`_ Nombre de la aduana
  * _`data[InvoicesProduct][0][ElementConcept][INFOADUANERA][1][fecha]`_ Fecha

o

> _**Cuenta Predial**_
  * _`data[InvoicesProduct][0][ElementConcept][predialAccount][numero]`_ Número de la cuenta


> _**COMPLEMENTOS POR FACTURA**_

> _**Donatarias**_
  * _`data[Invoice][Complements][DONATARIAS][ComplementDonatarias][fecha_autorizacion]`_ Fecha en la cual se autorizo _formato_ (AAAA-MM-DD)
  * _`data[Invoice][Complements][DONATARIAS][ComplementDonatarias][leyenda]`_ Leyenda que acompaña al complemento
  * _`data[Invoice][Complements][DONATARIAS][ComplementDonatarias][no_autorizacion]`_ Número de autorización

> _**Compra Venta de divisas**_
  * _`data[Invoice][Complements][COMVENDIVISA][ComplementComvendivisa][operacion]`_ Tipo de operación _Compra_,_Venta_

> _**Otros derechos e impuestos**_
  * _`data[Invoice][Complements][OTRDERIMP][ComplementOtrderimp][detail][0][imp_loc]`_ Impuesto que se esta aplicado _String_
  * _`data[Invoice][Complements][OTRDERIMP][ComplementOtrderimp][detail][0][importe]`_ Importe de impuesto
  * _`data[Invoice][Complements][OTRDERIMP][ComplementOtrderimp][detail][0][operacion]`_ Tipo de operacion _Retencion_,_Traslado_
  * _`data[Invoice][Complements][OTRDERIMP][ComplementOtrderimp][detail][0][tasa]`_ Tasa de impuesto
  * _`data[Invoice][Complements][OTRDERIMP][ComplementOtrderimp][total_de_retenciones]`_ Suma total de las retenciones
  * _`data[Invoice][Complements][OTRDERIMP][ComplementOtrderimp][total_de_traslados]`_ Suma total de los traslados

> _**Leyendas Fiscales**_
  * _`data[Invoice][Complements][LEYENDFISC][ComplementLeyendfisc][detail][1][disposicion_fiscal]`_ Disposicion Fiscal o ley que regula la leyenda
  * _`data[Invoice][Complements][LEYENDFISC][ComplementLeyendfisc][detail][1][norma]`_ No. de artículo que regula la leyenda
  * _`data[Invoice][Complements][LEYENDFISC][ComplementLeyendfisc][detail][1][texto_leyenda]`_ Texto de la leyenda

> _**Persona física integrante de coordinado**_
  * _`data[Invoice][Complements][PERFISCOORD][ComplementPerfiscoord][clave_vehicular]`_ Clave vehicular que corresponda a la versión del vehículo enajenado
  * _`data[Invoice][Complements][PERFISCOORD][ComplementPerfiscoord][placa]`_ Placa o número de folio del permiso del vehículo que corresponda
  * _`data[Invoice][Complements][PERFISCOORD][ComplementPerfiscoord][rfcpf]`_ RFC de la persona física integrante de coordinados, que opte por pagar el impuesto individualmente **(opcional)**

> _**Turista pasajero extranjero**_
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][empresa_transporte]`_ Empresa de transporte que lo ingresa a territorio nacional o lo traslada de salida
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][fecha_de_transito]`_ fecha y hora del Arribo o Salida del medio de transporte utilizado. Se expresa en la forma aaaa-mm-ddThh:mm:ss, de acuerdo con la especificación ISO 8601
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][id_transporte]`_ Identificador del medio de transporte usado, _ejemplo: número de vuelo_ **(opcional)**
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][nacionalidad]`_ nacionalidad del turista
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][numero_id]`_ Número de identificación (pasaporte, visa, etc.)
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][tipo_id]`_ Número de pasaporte
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][tipo_transito]`_ Expresar la información de la operación realizada
  * _`data[Invoice][Complements][TURPASEXTR][ComplementTurpasextr][via]`_ Expresar si es vía _Aérea_, _Marítima_ o _Terrestre_

> _**ADDENDAS**_

  * _`data[Invoice][addenda]`_  Addenda definida por el usuario puede ser texto plano o en formato XML


## Generación del CFD ##

Llamada:

  * _controller_ - invoices
  * _view_ - create\_cfd

Parámetros

  * id de la factura

Ejemplo: https://www.rfacil.com/invoices/create_cfd/23.xml?username=username&password=password&apikey=apikey

Datos POST:

Ninguno

## Descarga del XML ##

Llamada:

  * _controller_ - sat\_cfds
  * _view_ - xml

Parámetros

  * id del CFDI regresado al crear la factura

Ejemplo: https://www.rfacil.com/sat_cfds/xml/23.xml?username=username&password=password&apikey=apikey

## Descarga del PDF ##

Llamada:

  * _controller_ - sat\_cfds
  * _view_ - pdf

Parámetros

  * id del CFDI regresado al crear la factura

Devuelve el XML del CFDI en formato base64

Ejemplo: https://www.rfacil.com/sat_cfds/pdf/23.xml?username=username&password=password&apikey=apikey