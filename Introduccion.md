# Introducción #

Cualquier llamada tiene el siguiente formato REST

# Detalle #


`https://www.rfacil.com/`**controller**`/`**view**`/`**param1**`/`**param2**`.../`**paramn**`.xml?username=`**username**`&password=`**password**`&apikey=`**apikey**`&tax_reference=`**tax\_reference**

Obligatoriamente:

  * _username_ es el correo electrónico del usuario
  * _password_ es la contraseña asociada al usuario
  * _apikey_ es una clave de 32 caracteres separadas por guión, asignada a la aplicación

Opcionalmente

  * _tax\_reference_ es el RFC de la organización en la que estamos trabajando. Si no se proporciona, se toma la primera de las organizaciones del usuario.

# Controladores #

La API de rfácil actualmente soporta los siguientes controladores:

  * [Productos](Productos.md)
  * [Clientes](Clientes.md)
  * [Facturas](Facturas.md)