# Analisis-de-datos-usando-power-query-y-power-pivot
Problema a tratar: El gerente de una empresa requiere analizar el funcionamiento las importaciones y ventas de la empresa para identificar oportunidades de optimización. Para esto solicita que se relacionen todas las bases de datos que se poseen, para evaluar de manera exhaustiva la rentabilidad que dejan los productos, el país y el proveedor. También verificar cuales son los clientes más valiosos y sus patrones de compra. Por último identificar volumen y frecuencia de las ordenes, verificando estacionalidades.
Los datos que se poseen se muestran en la siguiente imagen:
![Datos](https://github.com/user-attachments/assets/1fb721f5-0d97-44cc-89ea-798b4a1b2ac7)

Luego de estar familiarizado con los datos, se puede observar que hay diferentes tablas en diferentes hojas que se relacionan entre sí, para vincular los datos de las diferentes tablas y crear una conexión es adecuado usar la herramienta Power Query, esta herramienta es útil para interrelacionar datos que se encuentran en diferentes tablas, además de otras funcionalidades que en el momento no serán necesarias. Se cargan los datos, se seleccionan los datos que se van a usar , se crea una consulta que relaciona las tablas y seleccionamos "cargar en", esto crea una nueva hoja donde se pueden observar todas las consultas que acabamos de crear.

![DatosPowerQuery](https://github.com/user-attachments/assets/4e90f746-ca30-4f58-9bbb-199b17138872)

Una vez cargados los datos como consultas usando Power Query, se implenta la herramienta Power Pivot con el objetivo de crear unos nuevos campos calculados en la hoja "DetallesOrden", estos campos calculados son: ImporteTotal, DescuentoTotal, CosteTotal y Margen, estos campos nos sirven para visualizar mejor el rendimiento en cuanto a beneficios y costos de los productos.
ImporteTotal: PrecioUnitario*Cantidad*(1-Descuento)  

DescuentoTotal: PrecioUnitario*Cantidad*Descuento  

CosteTotal: PrecioUnitarioCompra*Cantidad  

Margen: ImporteTotal/CosteTotal-1  

![DatosPowerPivot](https://github.com/user-attachments/assets/706ce1e5-895f-441c-a2b8-4d527e3a1a88)


Como se mencionó anteriormente, se usó Power Query para juntar datos de diferentes tablas, con la implementación de Power Pivot, es posible relacionar directamente las columnas de una tabla con otra de otra tabla, es importante que las relaciones se hagan con columnas que contengan los mismos datos, de esta manera se puede extraer valores que coincidan con dichas columnas, es decir, una relación de uno a muchos como lo podemos observar en el siguiente diagrama:
![DiagramaPowerPivot](https://github.com/user-attachments/assets/2519420a-a4a7-4dc5-9f9e-83d8effd4469)


Una vez establecidas las consultas con power query y establecidas las relaciones entre tablas con power pivot, se procede a crear, desde la misma ventana de power pivot, una tabla dinámica, esto nos permite visualizar las tablas que queremos relacionar, sus valores y relacionarlos, este procedimiento nos evita el uso de funciones como por ejemplo "BUSCARV".  

"Con todas las tablas relacionadas y los campos calculados necesarios, procedemos a realizar el primer análisis:  

El objetivo es visualizar los países a los que se ha solicitado un mayor importe según la categoría de productos. Esto nos permitirá identificar en qué países se debería aumentar el importe y qué productos generan los mayores gastos.  

La siguiente tabla muestra el importe de los productos por país, junto con los totales generales. Se ha implementado un formato condicional en cada columna de categoría para destacar el país con el mayor importe. Además, en los totales generales se utilizó un formato condicional con mapa de calor: los países con menor importe aparecen en rojo, mientras que aquellos con mayor importe se destacan en verde."

![ResultadosPaisCategoria](https://github.com/user-attachments/assets/b24cc60a-39d5-4e76-9620-36b9cf0d48bf)


Ahora, es ideal mostrar cuales de nuestros clientes nos ha solicitado mayor número de pedidos. Para esto, se creó una nueva tabla dinámica en la cual relacionamos las tablas de clientes y ordenes, a partir de esta, se creó un gráfico dinámico circular, utilizando la función de recuento, podemos observar el número de pedidos solicitados por cada cliente, esto nos ayuda a tener un balance general de cuales clientes generan mayor facturación o pedidos recurrentes. Se muestran los 10 clientes que más número de pedidos han solicitado.


![CantidadOrdenes2](https://github.com/user-attachments/assets/bb509c9c-8a49-4569-8ac6-0171fb150757)


Ahora que analizamos cuales de los clientes nos han solicitado un mayor número de pedidos, es pertinente evaluar cuáles de los vendedores han realizado un mayor número de venta, para esto vamos a analizar el precio total de ventas de cada uno. 
Usando los indicadores clave de rendimiento visualizaremos de forma sencilla cuales vendedores están siendo más proveen mayor beneficio y cuales un beneficio más bajo. A continuación se muestran los criterios que han sido elegidos para evaluar el rendimiento.  

Ventas menores a 76000: bajo beneficio  
Ventas entre 76000 y 150000: beneficio medio  
Ventas superiores a 150000: beneficio alto

![KPI](https://github.com/user-attachments/assets/be1e3b78-36a8-4f8d-b25b-fd2eab6769f6)

Establecidos los criterios de rendimiento, procedemos a observar, a través de una tabla muy sencilla, los vendedores que mayor y menor benficio están aportando en las ventas. Los vendedores están presentados por el apellido y en la columna "estado" un círculo con los colores rojos (bajo benficio), amarillo (beneficio medio), verde (beneficio alto). Podemos observar que los vendedores que menos ventas realizaron fueron Buchanan y Suyama, mientras que los que más beneficios aportaron fueron Leverling y Peacock.


![VentasVendedoresKPI](https://github.com/user-attachments/assets/94a1d46b-8b8c-4e5d-a438-e54a7aa22fcb)
