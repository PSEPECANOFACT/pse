| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número secuencial del ítem dentro del detalle de la nota de crédito. | Valor mínimo 1.  <br>Valor máximo 99. |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del producto/servicio. | Máximo 4 caracteres. |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del producto/servicio. | decimal(20,10). |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del producto/servicio. | Máximo 30 caracteres. |
| **DescripcionProducto**  <br>`obligatorio`  <br>`string` | Descripción del producto/servicio. | Máximo 250 caracteres. |
| **ValorUnitario**  <br>`obligatorio`  <br>`number` | Precio del producto/servicio sin IGV. Consignar indicar la mayor cantidad en la parte de decimal para que ayuden a la validación de calculos. | decimal(20,10). |
| **PrecioUnitario**  <br>`obligatorio`  <br>`number` | Precio de venta unitario por ítem (inc. IGV) | decimal(20,10). |
| **Igv**  <br>`obligatorio`  <br>`number` | Valor del IGV del ítem. | decimal(20,2). |
| **PorcentajeIgv**  <br>`obligatorio`  <br>`number` | Porcentaje del IGV del item. Debe ser expresado en formato entero.  <br>**Ejemplo:** 18. |  |
| **TipoAfectacionIgv**  <br>`obligatorio`  <br>`number` | [[Ver listado]](https://go.postman.co/workspace/86042989-f73c-4b23-80e9-41bbaddcdf08/documentation/7560300-d874b86e-3b0b-4fba-b21c-ef2e023b0062?entity=request-8f30dd2b-6933-4925-9ab2-2c93853e9919) |  |
| **ValorVenta**  <br>`obligatorio`  <br>`number` | Valor venta del item. Es la multiplicación de **Cantidad** por **ValorUnitario**. | decimal(20,2). |
| **Total**  <br>`obligatorio`  <br>`number` | Total del item. | .decimal(20,2). |