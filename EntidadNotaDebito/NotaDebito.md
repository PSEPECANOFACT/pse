### NotaDebito

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo de la nota de crédito. | Formato: \[Serie\]-\[Correlativo\]  <br>Serie: 4 caracteres.  <br>Correlativo: 8 caracteres.  <br>Máximo de caracteres: 13. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de la transacción de la nota de débito. | Formato: yyyy-MM-ddTHH:mm:ss |
| **Correo**  <br>`obligatorio`  <br>`string` | Correo electrónico al cual le llegará el CDR del CPE. | Se puede enviar una lista de correos utilizando el separador punto y coma (;) |
| **TipoMoneda**  <br>`obligatorio`  <br>`number` | Tipo de moneda.  <br>[[Ver listado]](../Listado/TipoMoneda.md) | Número entero. |
| **TipoNotaDebito**  <br>`obligatorio`  <br>`number` | Código del tipo de nota de débito.  <br>[[Ver listado]](../Listado/TipoNotaDebito.md) | Número entero. |
| **MotivoNotaDebito**  <br>`obligatorio`  <br>`string` | Motivo que sustenta la emisión de la nota de débito.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | De 1 a 500 caracteres. |
| **Emisor**  <br>`obligatorio`  <br>`objeto` | Datos del emisor.  <br>[[Ver entidad]](../Entidad/Emisor.md) |  |
| **Cliente**  <br>`obligatorio`  <br>`objeto` | Datos del adquiriente o usuario.  <br>[[Ver entidad]](../Entidad/Adquiriente.md) |  |
| **NumeroDocumentoReferencia**  <br>`obligatorio`  <br>`string` | Serie y correlativo del documento que modifica relacionado a la nota de débito. | Formato: \[Serie\]-\[Correlativo\]  <br>Serie: 4 caracteres.  <br>Correlativo: 8 caracteres.  <br>Máximo de caracteres: 13. |
| **TipoComprobanteReferencia**  <br>`obligatorio`  <br>`number` | Identificador del tipo de comprobante del documento que modifica relacionado a la nota de débito.  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Número entero. |
| **DetalleNotaDebito**  <br>`obligatorio`  <br>`objeto` | Datos del detalle o ítem de la nota de débito.  <br>[[Ver entidad]](../EntidadNotaDebito/NotaDebitoDetalle.md) |  |
| **Igv**  <br>`obligatorio`  <br>`number` | Monto total del IGV de la nota de débito. | decimal(14,2) |
| **IgvGratuito**  <br>`obligatorio`  <br>`number` | Monto total del IGV de la nota de débito de operaciones gratuitas. Calculado en base a los "Totales de Valor Venta" de las operaciones gravadas gratuitas. | decimal(14,2) |
| **TotalValorVentaOpeInafecta**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones inafectas de la nota de débito. | decimal(14,2) |
| **TotalValorVentaOpeExonerada**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones exoneradas de la nota de débito. | decimal(14,2) |
| **TotalValorVentaOpeGratuita**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones gratuitas de la nota de crédito. | decimal(14,2) |
| **TotalValorVentaOpeGravada**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones gravadas de la nota de débito. | decimal(14,2) |
| **FormaPago**  <br>`condicional`  <br>`string` | Forma de pago del comprobante cuando la condición de venta es 'Contado'.  <br>Por ejemplo: "Transferencia", "Tarjeta", "(Varias)", etc.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 100 caracteres. |
| **ImporteTotal**  <br>`obligatorio`  <br>`number` | Importe total de la nota de débito. | decimal(14,2) |
| **TipoCondicionVenta**  <br>`obligatorio`  <br>`number` | Identificador del tipo de condición de venta de la nota de débito o del documento relacionado.  <br>[[Ver listado]](../Listado/TipoCondicionVenta.md) | Número entero. |
| **FechaEmisionDocReferencia**  <br>`obligatorio`  <br>`string` | Fecha de la transacción del documento relacionado a la nota de débito. | Formato: yyyy-MM-dd. |
| **FechaVencimientoDocReferencia**  <br>`obligatorio`  <br>`string` | Fecha de vencimiento del documento relacionado a la nota de débito.  <br>Si la condición de venta es "Contado", la fecha de vencimiento es el mismo que la fecha de emisión. | Formato: yyyy-MM-dd. |
| **DireccionEntrega**  <br>`opcional`  <br>`string` | Dirección de llegada relacionado al comprobante de la venta.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 200 caracteres. |