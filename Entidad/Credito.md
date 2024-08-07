### Credito

| Propiedad                                         | Descripción                                                           | **Condición**                                            |
| ------------------------------------------------- | --------------------------------------------------------------------- | -------------------------------------------------------- |
| **NumeroCuota**  <br>`obligatorio`  <br>`number`  | Numero de la cuota                                                    | Valor mínimo 1.  <br>Valor máximo 999.                   |
| **ImporteCuota**  <br>`obligatorio`  <br>`number` | Importe de la cuota .                                                 | Debe ser menor o igual al importe total del comprobante. |
| **FechaPago**  <br>`obligatorio`  <br>`string`    | Fecha del pago de la cuota  <br>**Ejemplo:  <br>**yyyy-MM-ddTHH:mm:ss | Formato ISO 8601.                                        |