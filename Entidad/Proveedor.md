### Proveedor

| Propiedad                                           | Descripción                                                     | **Condición**             |
| --------------------------------------------------- | --------------------------------------------------------------- | ------------------------- |
| **NumeroRuc**  <br>`obligatorio`  <br>`string`      | Número de RUC del proveedor.                                    | Debe contener 11 dígitos. |
| **RazonSocial**  <br>`obligatorio`  <br>`string`    | Apellidos y nombres, denominación o razón social del proveedor.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 1500 caracteres.  |
| **NombreComercial**  <br>`opcional`  <br>`string`   | Nombre comercial del proveedor.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                                 | Máximo 1500 caracteres.  |
| **DireccionCompleta**  <br>`opcional`  <br>`string` | Dirección completa y detallada del proveedor.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                   | Máximo 100 caracteres.    |
| **Urbanizacion**  <br>`opcional`  <br>`string`      | Urbanización del proveedor.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                                     | Máximo 30 caracteres.     |
| **Ubigeo**  <br>`opcional`  <br>`string`            | Código de Ubigeo del proveedor.                                 | Debe contener 6 dígitos.  |