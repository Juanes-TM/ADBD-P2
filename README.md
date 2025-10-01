## ADBD-P2

### Descripción de las entidades definidas:

-**Medicamento:** Representa cualquier medicamento de la farmacia. Su clave primaria es el código de medicamento. Además, se describen los siguientes atributos: nombre, precio, tipo, unidades vendidas, unidades en stock y si requiere receta o no.

-**Laboratorio:** Representa cualquier laboratorio fabricante de medicamentos. Su clave primaria es el código del laboratorio. Por otro lado, se describen los atributos: nombre, telefono, nombre de la persona de contacto, dirección postal y fax.

-**Cliente:** Representa cualquier cliente que compra algun medicamento. Este puede ser un **cliente sin crédito** o un **cliente con crédito**, dependiendo si hace los pagos de los medicamentos a fin de mes o no. En el caso de los clientes con crédito, se registran los atributos adicionales: datos bancarios y fecha de pago.

 
