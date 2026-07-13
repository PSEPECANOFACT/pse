### CuentaCorriente

| Propiedad                                                    | Descripción                                                                 | **Condición**                 |
| ------------------------------------------------------------ | --------------------------------------------------------------------------- | ----------------------------- |
| **Banco**  <br>`obligatorio`  <br>`string`  | Banco al que pertenece la cuenta corriente | Máximo 100 caracteres. |
| **Moneda**  <br>`obligatorio`  <br>`string` | Moneda de la cuenta corriente                 | Máximo 20 caracteres. <br> Mínimo 3 caracteres. |
| **NumeroCuentaCorriente**  <br>`obligatorio`  <br>`string` |Número de cuenta corriente                 | Máximo 50 caracteres. <br> Mínimo 5 caracteres. |
| **CodigoCuentaInterbancaria**  <br>`opcional`  <br>`string` |Código interbancario de la cuenta corriente    | Máximo 50 caracteres. <br> Mínimo 5 caracteres. |
| **DireccionBanco**  <br>`opcional`  <br>`string` |Direccion del banco    | Máximo 200 caracteres. |
| **CodigoSwift**  <br>`opcional`  <br>`string` |Código SWIFT de la cuenta    | Máximo 20 caracteres |
| **EsDetraccion**  <br>`opcional`  <br>`bool` |Indicador si la cuenta corriente es para detracciones    | Por defecto false |
