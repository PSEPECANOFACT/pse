### Remitente - GRR

| Propiedad                                               | Descripción                                                                | **Condición**             |
| ------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------- |
| **Ruc**  <br>`obligatorio`  <br>`string`                | Número de RUC del remitente de la GRR.                                     | Debe contener 11 dígitos. |
| **RazonSocial**  <br>`obligatorio`  <br>`string`        | Apellidos y nombres, denominación o razón social del remitente de la GRR.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md)  | Máximo 250 caracteres.    |
| **DomFiscalDireccion**  <br>`obligatorio`  <br>`string` | Domicilio fiscal del remitente de la GRR (Dirección completa y detallada).  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 200 caracteres.    |
| **DomFiscalUbigeo**  <br>`obligatorio`  <br>`string`    | Código de Ubigeo del domicilio fiscal del remitente de la GRR.             | Debe contener 6 dígitos.  |