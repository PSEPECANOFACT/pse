### Cliente

| Propiedad                                                    | Descripción                                                                                            | **Condición**                 |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ----------------------------- |
| **TipoDocumentoIdentidad**  <br>`obligatorio`  <br>`number`  | Tipo de documento de identidad del cliente.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md) | Usar los valores del listado. |
| **ValorDocumentoIdentidad**  <br>`obligatorio`  <br>`string` | Número de documento de identidad del cliente según su **TipoDocumentoIdentidad**                       |                               |
| **RazonSocial**  <br>`obligatorio`  <br>`string`             | Razón social de la empresa del cliente                                                                 | Máximo 100 caracteres.        |
| **Direccion**  <br>`obligatorio`  <br>`string`               | Dirección del cliente                                                                                  | Máximo 100 caracteres.        |