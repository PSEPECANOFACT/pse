### GuiaRemitente

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **NumeroDocumento**  <br>`obligarorio`  <br>`string` | Serie y correlativo del comprobante.  <br>**Ejemplo:**  <br>T001-00000001 | Alfanumérico de 13 caracteres. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de emisión del comprobante.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **Correo**  <br>`opcional`  <br>`string` | Correos electrónicos de contacto, separados por punto y coma.  <br>**Ejemplo:**  <br>micorreo@midominio.com;tucorreo@tudominio.com | Máximo hasta 5 correos. |
| **Observacion**  <br>`opcional`  <br>`string` | Observaciones. | Alfanumérico de hasta 250 caracteres. |
| **Remitente**  <br>`obligatorio`  <br>`objeto` | Datos del remitente.  <br>[[Ver entidad]](../Entidad/RemitenteGRR.md) |  |
| **TipoComprobanteRelacionado**  <br>`condicional`  <br>`number` | Identificador del tipo de documento relacionado.  <br>[[Ver listado]](../Listado/TipoComprobanteRelacionadoGRR.md) | Catálogo 61. |
| **NumeroComprobanteRelacionado**  <br>`condicional`  <br>`string` | Número de documento relacionado. | Validaciones de la GRR. |
| **RucEmisorComprobanteRelacionado**  <br>`condicional`  <br>`string` | Número de RUC del emisor del documento relacionado. | Máximo 11 dígitos. |
| **Destinatario**  <br>`obligatorio`  <br>`objeto` | Datos del destinatario.  <br>[[Ver entidad]](../Entidad/DestinatarioGRR.md) |  |
| **Proveedor**  <br>`condicional`  <br>`objeto` | Datos del proveedor.  <br>[[Ver entidad]](../Entidad/ProveedorGRR.md) | Solo para los motivos de traslado 'Compra' y 'Recojo de bienes transformados'. |
| **MotivoTraslado**  <br>`obligatorio`  <br>`number` | Motivo del traslado.  <br>[[Ver listado]](../Listado/MotivoTraslado.md) | Catálogo 20. |
| **PesoBrutoTotalCarga**  <br>`obligatorio`  <br>`number` | Peso bruto total de la carga. | decimal(15,3) |
| **UnidadMedidaPesoBruto**  <br>`obligatorio`  <br>`string` | Unidad de medida del peso bruto. | Solo puede ser "KGM" (Kilogramos) o "TNE" (Toneladas). |
| **NumeroBultos**  <br>`condicional`  <br>`number` | Número de bultos o pallets. | Numérico hasta 6 dígitos.  <br>Solo para motivo de traslado 'Exportación'. |
| **ModalidadTransporte**  <br>`obligatorio`  <br>`number` | Modalidad de traslado o de transporte.  <br>[[Ver listado]](../Listado/ModalidadTransporte.md) | Catálogo 18. |
| **FechaInicioTraslado**  <br>`obligatorio`  <br>`string` | Fecha de inicio de traslado.  <br>**Ejemplo:**  <br>yyyy-MM-dd. | Debe ser mayor o igual que la fecha de emisión. |
| **Transportista**  <br>`condicional`  <br>`objeto` | Datos del transportista.  <br>[[Ver entidad]](../Entidad/TransportistaGRR.md) | Solo para modalidad de traslado 'Transporte público'. |
| **NumeroRegistroMtc**  <br>`condicional`  <br>`string` | Número de Registro MTC. | Alfanumérico hasta 20 caracteres.  <br>Solo letras mayúsculas y números.  <br>Solo para modalidad de traslado 'Transporte público'. |
| **Vehiculos**  <br>`condicional`  <br>`array` | Vehículos principal y secundarios.  <br>[[Ver entidad]](../Entidad/Vehiculo.md) | Hasta un máximo de 2 vehículos.  <br>Solo modalidad de traslado 'Transporte privado'. |
| **Conductores**  <br>`condicional`  <br>`array` | Conductores principal y secundarios.  <br>[[Ver entidad]](../Entidad/Conductor.md) | Hasta un máximo de 2 conductores.  <br>Solo modalidad de traslado 'Transporte privado'. |
| **UbigeoPartida**  <br>`obligatorio`  <br>`string` | UBIGEO de partida. | Numérico de 6 dígitos.  <br>Catálogo 13. |
| **DireccionPartida**  <br>`obligatorio`  <br>`string` | Dirección completa y detallada de partida. | Alfanumérico de 3 a 100 caracteres. |
| **CodLocalSunatPuntoPartida**  <br>`condicional`  <br>`string` | Código de establecimiento de punto de partida. | Numérico de 4 dígitos.  <br>Por defecto = "0000".  <br>Obligatorio para motivos de traslado 'Traslado entre establecimientos de la misma empresa' e 'Importación'. |
| **UbigeoLlegada**  <br>`condicional`  <br>`string` | UBIGEO de llegada. | Numérico de 6 dígitos.  <br>Catálogo 13.  <br>Solo para motivos de traslado diferente de 'Traslado emisor itinerante CP'. |
| **DireccionLlegada**  <br>`condicional`  <br>`string` | Dirección completa y detallada de llegada. | Alfanumérico de 3 a 100 caracteres.  <br>Solo para motivos de traslado diferente de 'Traslado emisor itinerante CP'. |
| **CodLocalSunatPuntoLlegada**  <br>`condicional`  <br>`string` | Código de establecimiento de punto de llegada. | Numérico de 4 dígitos.  <br>Obligatorio si el motivo de traslado es 'Traslado entre establecimientos de la misma empresa'. |
| **DetalleGuia**  <br>`obligatorio`  <br>`array` | Detalles del comprobante.  <br>[[Ver entidad]](../EntidadGuiaRemitente/GuiaRemitenteDetalle.md) |  |
| **VentaGuia**  <br>`condicional`  <br>`array` | Relación de ventas asociadas a la Guía de Remisión.  <br>[[Ver entidad]](../EntidadGuiaRemitente/GuiaRemitenteVenta.md) |  |
| **InformacionAdicional**  <br>`opcional`  <br>`array` |  Información adicional del comprobante.  <br>[[Ver entidad]](../Entidad/InformacionAdicional.md) |  |