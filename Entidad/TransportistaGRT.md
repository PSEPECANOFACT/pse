### Transportista - GRT

| Propiedad                                               | Descripción                                                                    | **Condición**             |
| ------------------------------------------------------- | ------------------------------------------------------------------------------ | ------------------------- |
| **Ruc**  <br>`obligatorio`  <br>`string`                | Número de RUC del transportista de la GRT.                                     | Debe contener 11 dígitos. |
| **RazonSocial**  <br>`obligatorio`  <br>`string`        | Apellidos y nombres, denominación o razón social del transportista de la GRT.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)  | Máximo 100 caracteres.    |
| **DomFiscalDireccion**  <br>`obligatorio`  <br>`string` | Domicilio fiscal del transportista de la GRT (Dirección completa y detallada).  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 100 caracteres.    |
| **DomFiscalUbigeo**  <br>`obligatorio`  <br>`string`    | Código de Ubigeo del domicilio fiscal del transportista de la GRT.             | Debe contener 6 dígitos.  |