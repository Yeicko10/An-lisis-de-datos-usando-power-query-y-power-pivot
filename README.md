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
