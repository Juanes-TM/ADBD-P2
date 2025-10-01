## ADBD-P2

### Descripción de las entidades definidas:

- **Medicamento:** Representa cualquier medicamento de la farmacia. Su clave primaria es el código. Además, se describen los siguientes atributos: nombre, precio, tipo, unidades vendidas, unidades en stock y si requiere o no una receta.

- **Laboratorio:** Representa cualquier laboratorio fabricante de medicamentos. Su clave primaria es el código del laboratorio. Por otro lado, se describen los atributos: nombre, telefono, nombre de la persona de contacto, dirección postal y fax.

- **Cliente:** Representa cualquier cliente que compra algun medicamento. Este puede ser un **cliente sin crédito** o un **cliente con crédito**, dependiendo si hace los pagos de los medicamentos a fin de mes o no. En el caso de los clientes con crédito, se registra el atributo datos bancarios.

### Descripción de cada una de las relaciones definidas con sus cardinalidades:

- **Fabrica:** Relaciona la entidad **Medicamento** con la entidad **Laboratorio**, indicando que un laboratorio fabrica medicamentos. En cuanto a la cardinalidad, un laboratorio puede fabricar cero o más medicamentos (0:N), y un medicamento puede ser fabricado por cero o mas laboratorios (0:N). Esto refleja que la farmacia puede tener medicamentos de distintos laboratorios y fabricarlos ella misma si hace falta.
  
- **Sustitución:** Relaciona la entidad **Medicamento** consigo misma. Posee el atributo **familia**, que indica la familia a la que pertenece un medicamento. Esta relación permite sustituir un medicamento por otro de la misma familia. En cuanto a la cardinalidad, un medicamento puede sustituir a uno o más medicamentos de la misma familia (1:N) y puede ser sustituido por uno o más medicamentos de la misma familia (1:N).

- **Compra:** Relaciona la entidad **Medicamento** con la entidad **Cliente**, indicando que un cliente compra medicamentos. Posee los atributos unidades compradas, fecha de compra y fecha de pago; esta última solo se aplica si el cliente tiene crédito. En cuanto a la cardinalidad, un cliente puede comprar uno o más medicamentos (1:N), y un mismo medicamento puede ser comprado por uno o más clientes (1:N).

### Descripción y ejemplos ilustrativos del dominio de cada uno de los atributos de las entidades y de las relaciones:

- **Medicamento:**
  - **Código:**  Identificador númerico del medicamento. INTEGER, ejemplo: 12345.
  - **Nombre:** Nombre del medicamento. VARCHAR(50), ejemplo: "Parecetamol", "Ibuprofeno", etc.
  - **Tipo:** Tipo de mecdicamento o presentación. VARCHAR(50), ejemplo: "jarabe", "comprimidos", etc.
  - **Unidades vendidas:** Cantidad de medicamento vendido. INTEGER, ejemplo: 120.
  - **Unidades en stock:** Cantidad de medicamento aún en stock. INTEGER, ejemplo: 400.
  - **Precio:** Precio del medicamento. DECIMAL(10,2), ejemplo: 4,50.
  - **Requiere receta?:** Si el medicamento necesita o no receta para ser comprado. BOOLEAN, ejemplo: FALSE.
   
- **Laboratorio:**
  - **Código:** Identificador númerico del laboratorio. INTEGER, ejemplo: 0001.
  - **Nombre:** Nombre del laboratorio. VARCHAR(50), ejemplo, "Pfizer".
  - **Teléfono:** Teléfono de contacto del laboratorio. VARCHAR(15), ejemplo: "+34 922345678".
  - **Persona de contacto:** Nombre de la persona de contacto. VARCHAR(50), ejemplo: "Carlos".
  - **Dirección postal:** Ubicación física del laboratorio. VARCHAR(200), ejemplo: "Calle Mayor, 45, Madrid".
  - **Fax:** Número de fax del laboratorio. VARCHAR(15), ejemplo: "+34 922345678".

- **Cliente con crédito:**
  - **Datos bancarios:** Datos bancarios del cliente con crédito. VARCHAR(100), ejemplo: "ES76 2100 0418 4502 0005 1332".

- **Sustitución (relación):**
  - **Familia:** Familia de medicamentos a la que pertenecen un grupo de medicamentos. VARCHAR(50), ejemplo: "Analgésicos" ("Ibuprofeno" puede sustituir a "Paracetamol" porque ambos pertenecen a la familia "Analgésicos").
 
- **Compra (relación):**
  - **Unidades compradas:** Unidades de un medicamento que un cliente compra. INTEGER, ejemplo: 3 (Un cliente compró 3 unidades de "Paracetamol").
  - **Fecha de compra:** Fecha en la que un medicamento es comprado por un cliente. DATE, ejemplo: 2025-09-25 (Un cliente compró 3 unidades de "Paracetamol" el 25/09/2025).
  - **Fecha de pago:** Fecha de pago de un medicamento comprado por un cliente con crédito. Date, ejemplo: 2025-09-20 (Un cliente con crédito pagó 3 unidades de "Paracetamol" el 20/09/2025).
   

