### Credito

| Propiedad                                         | Descripción                           | **Condición**                                            |
| ------------------------------------------------- | ------------------------------------- | -------------------------------------------------------- |
| **NumeroCuota**  <br>`obligatorio`  <br>`number`  | Identificador de la cuota.            | Valor mínimo 1.  <br>Valor máximo 999.                   |
| **ImporteCuota**  <br>`obligatorio`  <br>`number` | Monto del pago único o de las cuotas. | Debe ser menor o igual al 'importe total' del comprobante o 'importe neto de pago pendiente'. |
| **FechaPago**  <br>`obligatorio`  <br>`string`    | Fecha del pago único o de las cuotas.  <br>**Ejemplo:  <br>**yyyy-MM-ddTHH:mm:ss | Formato ISO 8601.                                        |