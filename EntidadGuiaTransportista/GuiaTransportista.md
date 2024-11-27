### GuiaTransportista

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **NumeroDocumento**  <br>`obligarorio`  <br>`string` | Serie y correlativo del comprobante.  <br>**Ejemplo:**  <br>V001-00000001 | Alfanumérico de 13 caracteres. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de emisión del comprobante.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **Correo**  <br>`obligatorio`  <br>`string` | Correos electrónicos de contacto, separados por punto y coma.  <br>**Ejemplo:**  <br>micorreo@midominio.com;tucorreo@tudominio.com | Máximo hasta 5 correos. |
| **Observacion**  <br>`opcional`  <br>`string` | Observaciones. | Alfanumérico de hasta 250 caracteres. |
| **Transportista**  <br>`obligatorio`  <br>`objeto` | Datos del transportista.  <br>[[Ver entidad]](../Entidad/TransportistaGRT.md) |  |
| **NumeroRegistroMtc**  <br>`obligatorio`  <br>`string` | Número de Registro MTC. | Alfanumérico hasta 20 caracteres.  <br>Solo letras mayúsculas y números. |
| **NumeroAutorizacionEspecial**  <br>`obligatorio`  <br>`string` | Número de autorización especial emitido por la entidad - Transportista. | Alfanumérico de 3 hasta 50 caracteres. |
| **EntidadEmisoraAutorizacion**  <br>`obligatorio`  <br>`number` | Entidad emisora de la autorización especial - Transportista.  <br>[[Ver listado]](../Listado/EntidadEmisoraAutorizacionEspecial.md) | Catálogo D-37. |
| **TipoComprobanteRelacionado**  <br>`condicional`  <br>`number` | Identificador del tipo de documento relacionado.  <br>[[Ver listado]](../Listado/TipoComprobanteRelacionadoGRT.md) | Catálogo 61. |
| **NumeroComprobanteRelacionado**  <br>`condicional`  <br>`string` | Número de documento relacionado. | Validaciones de la GRT. |
| **RucEmisorComprobanteRelacionado**  <br>`condicional`  <br>`string` | Número de RUC del emisor del documento relacionado. | Máximo 11 dígitos. |
| **Remitente**  <br>`obligatorio`  <br>`objeto` | Datos del remitente.  <br>[[Ver entidad]](../Entidad/RemitenteGRT.md) |  |
| **Destinatario**  <br>`obligatorio`  <br>`objeto` | Datos del destinatario.  <br>[[Ver entidad]](../Entidad/DestinatarioGRT.md) |  |
| **DetalleGuia**  <br>`obligatorio`  <br>`array` | Detalles del comprobante.  <br>[[Ver entidad]](../EntidadGuiaTransportista/GuiaTransportistaDetalle.md) |  |
| **UbigeoPartida**  <br>`obligatorio`  <br>`string` | UBIGEO de partida. | Numérico de 6 dígitos.  <br>Catálogo 13. |
| **DireccionPartida**  <br>`obligatorio`  <br>`string` | Dirección completa y detallada de partida. | Alfanumérico de 3 a 100 caracteres. |
| **CodLocalSunatPuntoPartida**  <br>`condicional`  <br>`string` | Código de establecimiento de punto de partida. | Numérico de 4 dígitos.  <br>Por defecto = "0000". |
| **UbigeoLlegada**  <br>`obligatorio`  <br>`string` | UBIGEO de llegada. | Numérico de 6 dígitos.  <br>Catálogo 13. |
| **DireccionLlegada**  <br>`obligatorio`  <br>`string` | Dirección completa y detallada de llegada. | Alfanumérico de 3 a 100 caracteres. |
| **CodLocalSunatPuntoLlegada**  <br>`obligatorio`  <br>`string` | Código de establecimiento de punto de llegada. | Numérico de 4 dígitos.  <br>Por defecto = "0000". |
| **Vehiculos**  <br>`obligatorio`  <br>`array` | Vehículos principal y secundarios.  <br>[[Ver entidad]](../Entidad/Vehiculo.md) | Hasta un máximo de 2 vehículos. |
| **Conductores**  <br>`obligatorio`  <br>`array` | Conductores principal y secundarios.  <br>[[Ver entidad]](../Entidad/Conductor.md) | Hasta un máximo de 2 conductores. |
| **FechaInicioTraslado**  <br>`obligatorio`  <br>`string` | Fecha de inicio de traslado.  <br>**Ejemplo:**  <br>yyyy-MM-dd. | Debe ser mayor o igual que la fecha de emisión. |
| **PesoBrutoTotalCarga**  <br>`obligatorio`  <br>`number` | Peso bruto total de la carga. | decimal(15,3) |
| **UnidadMedidaPesoBruto**  <br>`obligatorio`  <br>`string` | Unidad de medida del peso bruto. | Solo puede ser "KGM" (Kilogramos) o "TNE" (Toneladas). |
| **IndicadorRetornoVehiculoEnvaseVacio**  <br>`condicional`  <br>`number` | Indicador de retorno de vehículo con envases o embalajes vacíos. | Los valores son 1 (Sí) o 0 (No). |
| **IndicadorRetornoVehiculoVacio**  <br>`condicional`  <br>`number` | Indicador de retorno de vehículo vacío. | Los valores son 1 (Sí) o 0 (No). |
| **InformacionAdicional**  <br>`opcional`  <br>`array` |  Información adicional del comprobante.  <br>[[Ver entidad]](../Entidad/InformacionAdicional.md) | De consignarse esta sección, debe tener como máximo 100 elementos. |