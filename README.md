## ADBD-P2

### Descripción de las entidades definidas:

- **Medicamento:** Representa cualquier medicamento de la farmacia. Su clave primaria es el código. Además, se describen los siguientes atributos: nombre, precio, tipo, unidades vendidas, unidades en stock y si requiere o no una receta.

- **Laboratorio:** Representa cualquier laboratorio fabricante de medicamentos. Su clave primaria es el código del laboratorio. Por otro lado, se describen los atributos: nombre, telefono, nombre de la persona de contacto, dirección postal y fax.

- **Cliente:** Representa cualquier cliente que compra algun medicamento. Este puede ser un **cliente sin crédito** o un **cliente con crédito**, dependiendo si hace los pagos de los medicamentos a fin de mes o no. En el caso de los clientes con crédito, se registran los atributos adicionales: datos bancarios y fecha de pago.

### Descripción de cada una de las relaciones definidas con sus cardinalidades:

- **Fabrica:** Relaciona la entidad **Medicamento** con la entidad **Laboratorio**, indicando que un laboratorio fabrica medicamentos. En cuanto a la cardinalidad, un laboratorio puede fabricar cero o más medicamentos (0:N), y un medicamento puede ser fabricado por cero o mas laboratorios (0:N). Esto refleja que la farmacia puede tener medicamentos de distintos laboratorios y fabricarlos ella misma si hace falta.
  
- **Sustitución:** Relaciona la entidad **Medicamento** consigo misma. Posee el atributo **familia**, que indica la familia a la que pertenece un medicamento. Esta relación permite sustituir un medicamento por otro de la misma familia. En cuanto a la cardinalidad, un medicamento puede sustituir a uno o más medicamentos de la misma familia (1:N) y puede ser sustituido por uno o más medicamentos de la misma familia (1:N).

- **Compra:** Relaciona la entidad **Medicamento** con la entidad **Cliente**, indicando que un cliente compra medicamentos. Posee los atributos unidades compradas y fecha de compra. En cuanto a la cardinalidad, un cliente puede comprar uno o más medicamentos (1:N), y un mismo medicamento puede ser comprado por uno o más clientes (1:N).
