### Cliente

| Propiedad                                                     | Descripción                                                   | **Condición**               |
| ------------------------------------------------------------- | ------------------------------------------------------------- | --------------------------- |
| **TipoDocumentoIdentidad**  <br>`obligatorio`  <br>`number`   | Tipo de documento de identidad del cliente.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md) | Usar los valores del listado. |
| **NumeroDocumentoIdentidad**  <br>`obligatorio`  <br>`string` | Número de documento de identidad cliente.                     |                             |
| **RazonSocial**  <br>`obligatorio`  <br>`string`              | Apellidos y nombres, denominación o razón social del cliente.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 1500 caracteres.     |
| **NombreComercial**  <br>`opcional`  <br>`string`             | Nombre comercial del cliente.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                                 | Máximo 1500 caracteres.     |
| **DireccionCompleta**  <br>`opcional`  <br>`string`           | Dirección completa y detallada del cliente.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                   | Máximo 100 caracteres.      |
| **Urbanizacion**  <br>`opcional`  <br>`string`                | Urbanización del cliente.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                                     | Máximo 30 caracteres.       |
| **Ubigeo**  <br>`opcional`  <br>`string`                      | Ubigeo del cliente.                                           | Debe contener 6 caracteres. |