### Percepcion

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo del Comprobante de Percepción. | \<Serie>-\<Correlativo>.  <br>Serie: 4 caracteres.  <br>Correlativo: 8 dígitos.  <br> |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de la transacción del Comprobante de Percepción. | Formato: yyyy-MM-ddTHHmmss. |
| **Correo**  <br>`opcional`  <br>`string` | Correo electrónico al cual le llegará el CDR del CPE. | Se puede enviar una lista de correos utilizando el separador punto y coma (\;) |
| **IndicadorEmisionExcepcional**  <br>`opcional`  <br>`number` | Indicador de emisión excepcional.  <br>Si se activa, el Comprobante de Percepción solo puede relacionar al tipo de documento 'Factura', y solo uno. | Si se consigna un valor, este debe ser 1; de lo contrario, puede ser 0, null o no consignar ninguna línea (propiedad). |
| **Emisor**  <br>`obligatorio`  <br>`object` | Datos del Emisor.  <br>[[Ver entidad]](../Entidad/Emisor2.md) |  |
| **Cliente**  <br>`obligatorio`  <br>`object` | Datos del Cliente.  <br>[[Ver entidad]](../Entidad/Cliente.md) |  |
| **RegimenPercepcion**  <br>`obligatorio`  <br>`number` | Identificador del régimen de percepción, del cual se obtiene el porcentaje de percepción.  <br>[[Ver listado]](../Listado/RegimenPercepcion.md) | Número entero. |
| **Observaciones**  <br>`opcional`  <br>`string` | Observaciones.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo:  |
| **DetallePercepcion**  <br>`obligatorio`  <br>`array` | Datos de los detalles o ítems del Comprobante de Percepción.  <br>[[Ver entidad]](../EntidadPercepcion/PercepcionDetalle.md) | Mínimo de ítems: 1.  <br>Máximo de ítems: 100. |
| **ImporteTotalPercibidoMN**  <br>`obligatorio`  <br>`number` | Importe total percibido en moneda nacional.  <br>Es el importe obtenido de la suma de los 'Importes percibidos de cada ítem' en moneda nacional, sin considerar los 'Tipos de documentos relacionados 7 y 20'. | Número decimal mayor que cero.  <br>Formato: decimal(14,2) |
| **ImporteTotalCobradoMN**  <br>`obligatorio`  <br>`number` | Importe total cobrado en moneda nacional.  <br>Es el importe obtenido de la suma de los 'Importes totales cobrados de cada ítem' más el 'Monto de redondeo del importe total cobrado' (si es consignado) en moneda nacional, sin considerar los 'Tipos de documentos relacionados 7 y 20'. | Número decimal mayor que cero.  <br>Formato: decimal(14,2) |
| **MontoRedondeoImporteTotalCobradoMN**  <br>`condicional`  <br>`number` | Monto de redondeo del importe total cobrado.  <br>Si el 'Importe total cobrado' desea aplicarse con redondeo, el valor de redondeo debe consignarse en este campo. | Número decimal, cuyo valor absoluto es menor o igual que 1.  <br>Formato: decimal(14, 2).  <br>Mínimo: -1.00  <br>Máximo: 1.00 |
| **InformacionAdicional**  <br>`opcional`  <br>`array` |  Información adicional del comprobante.  <br>[[Ver entidad]](../Entidad/InformacionAdicional.md) | De consignarse esta sección, debe tener como máximo 100 elementos. |