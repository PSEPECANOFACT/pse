### FacturaDetalle

| Propiedad | Descripción | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número secuencial del ítem dentro del detalle del comprobante. | Valor mínimo: 1.  <br>Valor máximo: 99. |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del producto/servicio | Máximo 30 caracteres. |
| **Descripcion**  <br>`obligatorio`  <br>`string` | Descripción del producto/servicio.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 250 caracteres. |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del producto/servicio. | Entre 1 y 3 caracteres. |
| **UnidadMedidaAlias**  <br>`opcional`  <br>`string` | Unidad de medida alternativa del producto/servicio. Si el usuario lo deja en blanco, obtiene el código de la unidad de medida establecida por la SUNAT.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 35 caracteres. |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del producto/servicio. | decimal(20,10) |
| **ValorUnitario**  <br>`obligatorio`  <br>`number` | 'Valor unitario' del producto por ítem (para operaciones onerosas), o 'Valor referencial unitario' del producto por ítem (para operaciones gratuitas). En ambos casos, el precio es sin IGV.  <br>Es preferible enviar la mayor cantidad de decimales para hacer más preciso la validación de cálculos. | decimal(20,10) |
| **PrecioUnitario**  <br>`obligatorio`  <br>`number` | Precio del producto/servicio incluido el IGV. Este precio incluye el descuento por ítem.  <br>Si el tipo de afectación es gratuito, consignar cero (0). | decimal(20,10) |
| **TipoAfectacionIgv**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoAfectacionIgv.md) |  |
| **PorcentajeDescuento**  <br>`opcional`  <br>`number` | Porcentaje de descuento del ítem, expresado en formato decimal (por ejemplo: 0.05). | decimal(8, 3) |
| **ImporteDescuento**  <br>`opcional`  <br>`number` | Importe del descuento basado en el valor venta del item 'antes' de los impuestos. | decimal(14, 2) |
| **PorcentajeIgv**  <br>`obligatorio`  <br>`number` | Porcentaje del IGV del item. Debe ser expresado en formato entero.  <br>**Ejemplo:**  <br>18 (para 18 %) |  |
| **ValorVenta**  <br>`obligatorio`  <br>`number` | Valor venta del item. Es la multiplicación de **Cantidad** por **ValorUnitario**, incluido el "descuento por ítem", si es que tiene. | decimal(20,2) |
| **Igv**  <br>`obligatorio`  <br>`number` | Valor del IGV del ítem, incluido el "descuento por ítem" (si es que tiene). | decimal(20,2) |
| **Total**  <br>`obligatorio`  <br>`number` | Total del item. | decimal(20,2) |