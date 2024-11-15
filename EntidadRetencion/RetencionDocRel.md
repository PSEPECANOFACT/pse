### RetencionDocRel

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **TipoDocumento**  <br>`obligatorio`  <br>`number` | Tipo de documento relacionado.  <br>[[Ver listado]](../Listado/TipoComprobanteRelacionadoRetencion.md) | Número entero. |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y número del documento relacionado. | \<Serie\>-\<Correlativo\>. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha de emisión del documento relacionado. | Debe ser menor o igual que la 'Fecha de emisión' del comprobante de retención.  <br>Formato: yyyy-MM-dd. |
| **TipoMoneda**  <br>`obligatorio`  <br>`number`  | Tipo de moneda del documento relacionado.  <br>[[Ver listado]](../Listado/TipoMoneda.md) | Número entero. |
| **ImporteTotal**  <br>`obligatorio` <br>`number` | Importe total del documento relacionado. | Número decimal mayor que cero.  <br>Formato: decimal(14,2) |