### ResumenDiario  `(uso interno de Pecano)`

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **Identificador**  <br>`obligatorio`  <br>`string` | Identificador del resumen. | Formato: RC-\[0-9\]{8}-\[0-9\]{1-5} |
| **FechaGeneracion**  <br>`obligatorio`  <br>`string` | Fecha de generación del resumen. | Formato: YYYY-MM-DD.  <br>Esta fecha debe ser menor o igual a la fecha del servidor. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha de emisión de los documentos. | Formato: YYYY-MM-DD.  <br>La 'FechaEmision' debe ser menor o igual que 'FechaGeneracion'. |
| **Emisor**  <br>`obligatorio`  <br>`object` | Datos del emisor.  <br>[[Ver entidad]](../Entidad/Emisor3.md) |  |
| **DetalleResumenDiario**  <br>`obligatorio`  <br>`array` | Datos de los detalles o ítems del Resumen Diario.  <br>[[Ver entidad]](../EntidadResumenDiario/ResumenDiarioDetalle.md) | Mínimo de ítems: 1.  <br>Máximo de ítems: 100. |
| **Correo**  <br>`opcional`  <br>`string` | Correo electrónico al cual le llegará el CDR del CPE. | Se puede enviar una lista de correos utilizando el separador punto y coma (\;) |
| **InformacionAdicional**  <br>`opcional`  <br>`array` | Información adicional.  <br>[[Ver entidad]](../Entidad/InformacionAdicional.md) | De consignarse esta sección, debe tener como máximo 100 elementos. |