### Emisor

| Propiedad                                               | Descripción                                                                     | **Condición**             |
| ------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------- |
| **Ruc**  <br>`obligatorio`  <br>`string`                | Número de RUC del emisor.                                                       | Debe contener 11 dígitos. |
| **RazonSocial**  <br>`obligatorio`  <br>`string`        | Apellidos y nombres, denominación o razón social del emisor.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                    | Máximo 1500 caracteres.   |
| **NombreComercial**  <br>`obligatorio`  <br>`string`    | Nombre comercial del emisor.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                                                    | Máximo 1500 caracteres.   |
| **DomFiscalDireccion**  <br>`obligatorio`  <br>`string` | Domicilio fiscal del emisor (Dirección completa y detallada).  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)                   | Máximo 200 caracteres.    |
| **DomFiscalUbigeo**  <br>`obligatorio`  <br>`string`    | Código de Ubigeo del domicilio fiscal del emisor.                               | Debe contener 6 dígitos.  |
| **CodLocalSunat**  <br>`obligatorio`  <br>`string`      | Código asignado por la SUNAT para el establecimiento anexo declarado en el RUC. | Debe contener 4 dígitos.  |