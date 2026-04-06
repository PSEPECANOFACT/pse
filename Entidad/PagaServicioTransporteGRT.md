### PagaServicioTransporte - GRT

| Propiedad                                                    | Descripción                                                                 | **Condición**                 |
| ------------------------------------------------------------ | --------------------------------------------------------------------------- | ----------------------------- |
| **TipoDocumentoIdentidad**  <br>`obligatorio`  <br>`number`   | Tipo de documento de identidad de quien paga el servicio.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md) | Usar los valores del listado |
| **NumeroDocumentoIdentidad**  <br>`obligatorio`  <br>`string` | Número de documento de identidad de quien paga el servicio. | Máximo 15 caracteres. |
| **RazonSocial**  <br>`obligatorio`  <br>`string`              | Apellidos y nombres, denominación o razón social de quien paga el servicio.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 250 caracteres. |