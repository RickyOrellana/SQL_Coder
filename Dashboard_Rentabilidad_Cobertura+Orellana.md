## Creación de Base de un Dashboard de Rentabilidad y Zonas de Cobertura del negocio Automotriz.

## Problema:

El equipo comercial de Repuestos automotrices solicita una base para la creación de un tablero de rentabilidad donde se pueda ver la evolución de la rentabilidad segmentado por linea de producto y las zonas de cobertura por linea de producto en todo el pais. Es por ello que nos enfrentamos ante la necesidad de diseñar una base de datos eficiente que pueda manejar todas las operaciones relacionadas al calculo de rentabilidad y alcance geografico del negocio.

### Descripción del Problema:

1. **Gestión de Clientes y Ventas**: Necesitamos una base de datos que nos permita registrar la información detalladas de las ventas en un periodo de tiempo, asi como tambien la información al detalle de los clientes, incluyendo su ubicación y datos personales.

2. **Gestión de Información de Productos**: Es importante poder clasificar las productos según su tipo, es decir a que linea de producto pertenece, kits de distribución, bombas de agua, rodamientos, etc. Esto nos ayudará a organizar mejor la segmentación de la información para cumplir con las necesidades del equipo comercial. Ademas es de suma importancia para el calculo de rentabilidad, poder definir el costo de cada producto.

3. **Gestión de Proveedores**: La base de datos debe brindarnos información detallada sobre los proveedores ya que según su tipo y origen, se modificará el coeficiente de landeo para generar el costo final del producto.

4. **Gestión de Informacion Geográfica**: La base debe incorporar información geografica detallada, tal como el código postal y coordenadas, con el fin de poder armar un mapa de calor en el dashboard.


### Objetivo:

Diseñar e implementar una base de datos relacional que satisfaga todas las necesidades de información necesaria para el calculo de rentabilidad y definición de las zonas de cobertura. Esta base de datos deberá ser eficiente, escalable y fácil de mantener, permitiendo una gestión ágil y precisa de la información.

### Tablas:

1. **VENTAS**:
   - Almacena información sobre las ventas que realizan los clientes en un período de tiempo.
   - Atributos: ID_VENTA, FECHA, ID_PRODUCTO, CANTIDAD, ID_CLIENTE, PRECIO.

2. **PRODUCTOS**:
   - Contiene información sobre los productos disponibles para la venta
   - Atributos: ID_PRODUCTO, ID_LINEA_PRODUCTO, ID_SUPPLIER, COSTO_PRODUCTO.

3. **LINK_VENTA_PRODUCTO**:
   - Concatena la información de facturas y productos.
   - Atributos: ID_PRODUCTO, ID_VENTA, CANTIDAD.

4. **CLIENTES**:
   - Guarda información sobre los Clientes.
   - Atributos: ID_CLIENTE, NOMBRE_CLIENTE, EMAIL, ID_UBICACIÓN.

5. **SUPPLIER**:
   - Contiene información sobre los proveedores de los productos.
   - Atributos: ID_SUPPLIER, NOMBRE_SUPPLIER, ID_TIPO_SUPPLIER, ID_ORIGEN.

6. **TIPO SUPPLIER**:
   - Define diferentes tipos de supplier para clasificarlos y poder definir que costos se asocian segun su clasificación.
   - Atributos: ID_TIPO_SUPPLIER, TIPO_SUPPLIER.

7. **TIPO_PRODUCTO**:
   - Contiene información sobre los tipos de productos.
   - Atributos: ID_TIPO_PRODUCTO, LINEA_PRODUCTO.

8. **ORIGEN**:
   - Contiene información de costos asociados segun el origen del producto.
   - Atributos: ID_ORIGEN, NOMBRE_ORIGEN, COEFICIENTE_LANDEO.

9. **UBICACIÓN**:
   - Guarda información sobre la ubicación de los clientes.
   - Atributos: ID_UBICACION, CODIGO_POSTAL, ID_PROVINCIA, NOMBRE_CIUDAD, COORDENADAS.

10. **PROVINCIAS**:
   - Contiene información sobre las provincias.
   - Atributos: ID_PROVINCIA, NOMBRE_PROVINCIA.


