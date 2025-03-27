### NotaCredito

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo de la nota de crédito. | Formato: \[Serie\]-\[Correlativo\]  <br>Serie: 4 caracteres.  <br>Correlativo: 8 caracteres.  <br>Máximo de caracteres: 13. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de la transacción de la nota de crédito. | Formato: yyyy-MM-ddTHH:mm:ss |
| **Correo**  <br>`obligatorio`  <br>`string` | Correos electrónicos de contacto, separados por punto y coma.  <br>**Ejemplo:**  <br>micorreo@midominio.com;tucorreo@tudominio.com | Máximo hasta 5 correos. |
| **TipoMoneda**  <br>`obligatorio`  <br>`number` | Tipo de moneda.  <br>[[Ver listado]](../Listado/TipoMoneda.md) | Número entero. |
| **TipoNotaCredito**  <br>`obligatorio`  <br>`number` | Código del tipo de nota de crédito.  <br>[[Ver listado]](../Listado/TipoNotaCredito.md) | Número entero. |
| **MotivoNotaCredito**  <br>`obligatorio`  <br>`string` | Motivo que sustento la emisión de la nota de crédito.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | De 1 a 500 caracteres. |
| **Emisor**  <br>`obligatorio`  <br>`objeto` | Datos del emisor.  <br>[[Ver entidad]](../Entidad/Emisor.md) |  |
| **Cliente**  <br>`obligatorio`  <br>`objeto` | Datos del adquiriente o usuario.  <br>[[Ver entidad]](../Entidad/Adquiriente.md) |  |
| **NumeroDocumentoReferencia**  <br>`obligatorio`  <br>`string` | Serie y correlativo del documento que modifica relacionado a la nota de crédito. | Formato: \[Serie\]-\[Correlativo\]  <br>Serie: 4 caracteres.  <br>Correlativo: 8 caracteres.  <br>Máximo de caracteres: 13. |
| **TipoComprobanteReferencia**  <br>`obligatorio`  <br>`number` | Identificador del tipo de comprobante del documento que modifica relacionado a la nota de crédito.  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Número entero. |
| **DetalleNotaCredito**  <br>`obligatorio`  <br>`objeto` | Datos del detalle o ítem de la nota de crédito.  <br>[[Ver entidad]](../EntidadNotaCredito/NotaCreditoDetalle.md) |  |
| **Igv**  <br>`obligatorio`  <br>`number` | Monto total del IGV de la nota de crédito. | decimal(14,2) |
| **TotalValorVentaOpeInafecta**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones inafectas de la nota de crédito. | decimal(14,2) |
| **TotalValorVentaOpeExonerada**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones exoneradas de la nota de crédito. | decimal(14,2) |
| **TotalValorVentaOpeGratuita**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones gratuitas de la nota de crédito. | decimal(14,2) |
| **TotalValorVentaOpeGravada**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones gravadas de la nota de crédito. | decimal(14,2) |
| **ImporteTotal**  <br>`obligatorio`  <br>`number` | Importe total de la nota de crédito. | decimal(14,2) |
| **DetalleCredito**  <br>`condicional`  <br>`objeto` | Información adicional de la forma de pago al crédito.  <br>[[Ver entidad]](../Entidad/Credito.md) | Solo cuando el código de afectación al IGV es: 13. |
| **TipoCondicionVenta**  <br>`obligatorio`  <br>`number` | Identificador del tipo de condición de venta de la nota de crédito o del documento relacionado.  <br>[[Ver listado]](../Listado/TipoCondicionVenta.md) | Número entero. |
| **FechaEmisionDocReferencia**  <br>`obligatorio`  <br>`string` | Fecha de la transacción del documento relacionado a la nota de crédito. | Formato: yyyy-MM-dd. |
| **FechaVencimientoDocReferencia**  <br>`obligatorio`  <br>`string` | Fecha de vencimiento del documento relacionado a la nota de crédito.  <br>Si la condición de venta es "Crédito", la fecha de vencimiento es el mismo que la fecha de emisión. | Formato: yyyy-MM-dd. |
| **DireccionEntrega**  <br>`opcional`  <br>`string` | Dirección de llegada relacionado al comprobante de la venta.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 200 caracteres. |