### Retencion

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo del Comprobante de Retención. | \<Serie>-\<Correlativo>.  <br>Serie: 4 caracteres.  <br>Correlativo: 8 dígitos.  <br> |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de la transacción del Comprobante de Retención. | Formato: yyyy-MM-ddTHHmmss. |
| **Correo**  <br>`opcional`  <br>`string` | Correo electrónico al cual le llegará el CDR del CPE. | Se puede enviar una lista de correos utilizando el separador punto y coma (\;) |
| **Emisor**  <br>`obligatorio`  <br>`object` | Datos del Emisor.  <br>[[Ver entidad]](../Entidad/Emisor.md) |  |
| **Proveedor**  <br>`obligatorio`  <br>`object` | Datos del Proveedor.  <br>[[Ver entidad]](../Entidad/Emisor.md) |  |
| **RegimenRetencion**  <br>`obligatorio`  <br>`number` | Identificador del régimen de retención, del cual se obtiene la tasa de retención.  <br>[[Ver listado]](../Listado/RegimenRetencion.md) | Número entero. |
| **Observaciones**  <br>`opcional`  <br>`string` | Observaciones. | Máximo:  |
| **DetalleRetencion**  <br>`obligatorio`  <br>`array` | Datos de los detalles o ítems del Comprobante de Retención.  <br>[[Ver entidad]](../EntidadRetencion/RetencionDetalle.md) | Mínimo de ítems: 1.  <br>Máximo de ítems: 100. |
| **ImporteTotalRetenidoMN**  <br>`obligatorio`  <br>`number` | Importe total retenido en moneda nacional.  <br>Es el importe obtenido de la suma de los 'Importes retenidos de cada ítem' en moneda nacional, excluyendo los 'Tipos de documentos relacionados 7 y 20'. | Número decimal mayor que cero.  <br>Formato: decimal(14,2) |
| **ImporteTotalPagadoMN**  <br>`obligatorio`  <br>`number` | Importe total pagado en moneda nacional.  <br>Es el importe obtenido de la suma de los 'Importes totales pagados de cada ítem' más el 'Monto de redondeo del importe total pagado' (si es consignado) en moneda nacional, excluyendo los 'Tipos de documentos relacionados 7 y 20'. | Número decimal mayor que cero.  <br>Formato: decimal(14,2) |
| **MontoRedondeoImporteTotalPagadoMN**  <br>`condicional`  <br>`number` | Monto de redondeo del importe total pagado.  <br>Si el 'Importe total pagado' desea aplicarse con redondeo, el valor de redondeo debe consignarse en este campo. | Número decimal, cuyo valor absoluto es menor o igual que 1.  <br>Formato: decimal(14, 2).  <br>Mínimo: -1.00  <br>Máximo: 1.00 |
| **InformacionAdicional**  <br>`opcional`  <br>`array` |  Información adicional del comprobante.  <br>[[Ver entidad]](../Entidad/InformacionAdicional.md) | De consignarse esta sección, debe tener como máximo 100 elementos. |