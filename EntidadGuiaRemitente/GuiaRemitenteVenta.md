### GuiaRemitenteVenta

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de orden del ítem. | Caracteres numéricos de hasta 2 dígitos (numeración secuencial). |
| **TipoComprobanteVenta**  <br>`obligatorio`  <br>`number` | Identificador del tipo de comprobante de venta relacionado.  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Solo:  <br>\- \[10\]: Factura.  <br>\- \[20\]: Boleta. |
| **NumeroComprobanteVenta**  <br>`obligatorio`  <br>`string` | Serie y correlativo del comprobante de venta relacionado. | Alfanumérico de 13 caracteres.  <br>Formato: - |
| **FechaEmisionVenta**  <br>`obligatorio`  <br>`string` | Fecha de emisión del comprobante de venta relacionado. | Formato: "yyyy-MM-dd" |