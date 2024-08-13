### BoletaAnticipo

| Propiedad | Descripción | Condición |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Numero de ítem del detalle de la lista de anticipos. Debe ser secuencual. | Mínimo: 1.  <br>Máximo 99. |
| **ImporteAnticipo**  <br>`obligatorio`  <br>`number` | Monto del anticipo usado (incluye Impuesto). | decimal(14, 2) |
| **FechaEmisionAnticipo**  <br>`obligatorio`  <br>`datetime` | Fecha de emisión del anticipo.  <br>**Ejemplo:  <br>**yyyy-MM-dd |  |
| **NumeroDocumentoAnticipo**  <br>`obligatorio`  <br>`string` | Numero de documento del anticipo.  <br>**Ejemplo:  <br>**F001-00000001 | Máximo 13 caracteres. |
| **TipoComprobanteAnticipo**  <br>`obligatorio`  <br>`objeto` | Identificador del tipo de comprobante del anticipo de la venta.  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Constante: 10 |