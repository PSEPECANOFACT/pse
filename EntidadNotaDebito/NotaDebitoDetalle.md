### NotaDebitoDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número secuencial del ítem dentro del detalle de la nota de débito. | Valor mínimo 1.  <br>Valor máximo 99. |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del producto/servicio. | Entre 1 y 3 caracteres. |
| **UnidadMedidaAlias**  <br>`opcional`  <br>`string` | Unidad de medida alternativa del producto/servicio. Si el usuario lo deja en blanco, obtiene el código de la unidad de medida establecida por la SUNAT.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 35 caracteres. |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del producto/servicio. | decimal(20,10). |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del producto/servicio. | Máximo 30 caracteres. |
| **DescripcionProducto**  <br>`obligatorio`  <br>`string` | Descripción del producto/servicio.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 500 caracteres. |
| **ValorUnitario**  <br>`obligatorio`  <br>`number` | Precio del producto/servicio sin IGV. Consignar indicar la mayor cantidad en la parte de decimal para que ayuden a la validación de calculos. | decimal(20,10). |
| **PrecioUnitario**  <br>`obligatorio`  <br>`number` | Precio de venta unitario por ítem (inc. IGV) | decimal(20,10). |
| **Igv**  <br>`obligatorio`  <br>`number` | Valor del IGV del ítem. | decimal(20,2). |
| **PorcentajeIgv**  <br>`obligatorio`  <br>`number` | Porcentaje del IGV del item. Debe ser expresado en formato entero.  <br>**Ejemplo:** 18. |  |
| **TipoAfectacionIgv**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoAfectacionIgv.md) |  |
| **ValorVenta**  <br>`obligatorio`  <br>`number` | Valor venta del item. Es la multiplicación de **Cantidad** por **ValorUnitario**. | decimal(20,2). |
| **Total**  <br>`obligatorio`  <br>`number` | Total del item. | .decimal(20,2). |