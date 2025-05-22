### ComunicacionBaja

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **Identificador**  <br>`obligatorio`  <br>`string` | Identificador de la comunicación. | Formato: RA-\[0-9\]{8}-\[0-9\]{1-5} |
| **FechaGeneracion**  <br>`obligatorio`  <br>`string` | Fecha de generación de la comunicación. | Formato: YYYY-MM-DD.  <br>Esta fecha debe ser menor o igual a la fecha del servidor. |
| **FechaEmision**  <br>`obligatorio`  <br>`string`  | Fecha de generación del documento dado de baja (fecha de emisión del documento). | Formato: YYYY-MM-DD.  <br>La 'FechaEmision' debe ser menor o igual que 'FechaGeneracion'. |
| **Emisor**  <br>`obligatorio`  <br>`object` | Datos del emisor.  <br>[[Ver entidad]](../Entidad/Emisor3.md) |  |
| **DetalleComunicacionBaja**  <br>`obligatorio`  <br>`array` | Datos de los detalles o ítems de la Comunicación de Baja.  <br>[[Ver entidad]](../EntidadComunicacionBaja/ComunicacionBajaDetalle.md) | Mínimo de ítems: 1.  <br>Máximo de ítems: 100. |
| **Correo**  <br>`opcional`  <br>`string` | Correo electrónico al cual le llegará el CDR del CPE. | Se puede enviar una lista de correos utilizando el separador punto y coma (\;) |
| **InformacionAdicional**  <br>`opcional`  <br>`array` | Información adicional.  <br>[[Ver entidad]](../Entidad/InformacionAdicional.md) | De consignarse esta sección, debe tener como máximo 100 elementos. |