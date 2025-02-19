### Cliente (Adquiriente)

| Propiedad                                                    | Descripción                                                                 | **Condición**                 |
| ------------------------------------------------------------ | --------------------------------------------------------------------------- | ----------------------------- |
| **TipoDocumentoIdentidad**  <br>`obligatorio`  <br>`number`  | Tipo de documento de identidad del adquiriente o usuario.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md) | Usar los valores del listado. |
| **ValorDocumentoIdentidad**  <br>`obligatorio`  <br>`string` | Número de documento de identidad del adquiriente o usuario.                 |                               |
| **RazonSocial**  <br>`obligatorio`  <br>`string`             | Apellidos y nombres, denominación o razón social del adquiriente o usuario.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 100 caracteres.        |
| **Direccion**  <br>`obligatorio`  <br>`string`               | Dirección del adquiriente o usuario (Dirección completa y detallada).  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)       | Máximo 100 caracteres.        |