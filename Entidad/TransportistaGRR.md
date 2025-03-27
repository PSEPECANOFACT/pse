### Transportista - GRR

| Propiedad                                                    | Descripción                                                                  | **Condición**                 |
| ------------------------------------------------------------ | ---------------------------------------------------------------------------- | ----------------------------- |
| **TipoDocumentoIdentidad**  <br>`obligatorio`  <br>`number`  | Tipo de documento de identidad del transportista de la GRR.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md) | Usar los valores del listado. |
| **ValorDocumentoIdentidad**  <br>`obligatorio`  <br>`string` | Número de RUC del transportista de la GRR.                 | 11 dígitos. |
| **RazonSocial**  <br>`obligatorio`  <br>`string`             | Apellidos y nombres, denominación o razón social del transportista de la GRR.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 250 caracteres.        |