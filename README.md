# Analisis-de-datos-usando-power-query-y-power-pivot
Problema a tratar: El gerente de una empresa está interesado en conocer cómo va su estrategia de marketing para verificar si ha funcionado o requiere otro enfoque. Para esto, se reune con los analistas para solicitar un informe que revele datos significativos para la toma decisiones. El objetivo es proporcionarle información que pueda usar para tomar desiciones más significativas, para esto se le mostrará tendencias, desglose de diferentes categorias, países donde hubo mayor importe, de esta forma se determinará si se está generando buenos ingresos y qué factores podrían estar afectando las ventas.
Primero analizaremos los datos que poseemos:
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

Ahora que tenemos todas las tablas relacionadas y los campos calculados necesarios, procedemos a realizar el primer análisis:
Queremos visualizar cuales son los países a los que se ha hecho un mayor importe según la categoría de productos, de esta manera podemos determinar en cuales países se debe aumentar el importe, así como los productos que mayor gastos genera.
En la siguiente tabla podemos visualizar el importe de productos a los diferentes países con sus totales generales, en cada columna de categría se implementó un formato condicional para ver en qué país fue superior el importe, y en los totales generales un formato condicional con mapa de calor para mostrar los países que menos importe tuvieron (color rojo) y los que mayor importe tuvieron (color verde).

![ResultadosPaisCategoria](https://github.com/user-attachments/assets/b24cc60a-39d5-4e76-9620-36b9cf0d48bf)

