### LoteProducto

| **Propiedad**  | **Descripción** | **Condición** |
| - | - | - |
| **IdItemLote**  <br>`obligatorio`  <br>`number` | Numero de ítem del detalle de lotes. | Número secuencial.  <br>Mínimo: 1.  <br>Máximo: 99. |
| **NumeroLote**  <br>`obligatorio`  <br>`string` | Número del lote del producto.  <br>Dato alfanumérico. | Máximo de 20 caracteres alfanuméricos. |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad de productos del lote para el detalle del CPE. | decimal(20, 10) |
| **FechaExpiracion**  <br>`obligatorio`  <br>`string` | Fecha de expiración de los productos que pertenecen al lote.  <br>Ejemplo: yyyy-MM-ddTHH:mm:ss | Formato ISO 8601 |