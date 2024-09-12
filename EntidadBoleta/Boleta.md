### Boleta

| Propiedad | Descripción | Condición |
| --- | --- | --- |
| **Emisor**  <br>`obligatorio`  <br>`object` | [[Ver objeto]](../Entidad/Emisor.md) |  |
| **Cliente**  <br>`obligatorio`  <br>`object` | [[Ver objeto]](../Entidad/Cliente.md) |  |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo del comprobante  <br>**Ejemplo:  <br>**B001-00000001 | Máximo 13 caracteres. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de la emisión del comprobante.  <br>**Ejemplo:  <br>**yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **FechaVencimiento**  <br>`obligatorio`  <br>`string` | Fecha y hora del vencimiento del comprobante.  <br>**Ejemplo:  <br>**yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **TipoOperacion**  <br>`obligatorio`  <br>`string` | [[Ver listado]](../Listado/TipoOperacion.md) |  |
| **TipoMoneda**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoMoneda.md) |  |
| **TipoCondicionVenta**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoCondicionVenta.md) |  |
| **SubCondicion**  <br>`opcional`  <br>`string` |  | Máximo hasta 50 caracteres. |
| **FormaPago**  <br>`opcional`  <br>`string` | Aplica sólo a ventas con la condición | Máximo hasta 50 caracteres. |
| **Correo**  <br>`opcional`  <br>`string` | Correos electrónicos de contacto, separados por punto y coma.  <br>**Ejemplo:**  <br>[joaquin@pecano.pe;franciscoli@pecano.pe;oscar@pecano.pe](https://mailto:joaquin@pecano.pe) | Máximo hasta 5 correos. |
| **ObservacionVenta**  <br>`opcional`  <br>`string` | Observación sobre la venta. | Máximo hasta 100 caracteres. |
| **TipoCambio**  <br>`opcional`  <br>`number` | Tipo de cambio de la operación | Si TipoMoneda es diferente de Soles, este campo se vuelve obligatorio. |
| **DireccionEntrega**  <br>`opcional`  <br>`string` | Dirección de entrega del comprobante de venta. | Máximo: 200 caracteres. |
| **DetalleBoleta**  <br>`obligatorio`  <br>`array` | [[Ver entidad]](../EntidadBoleta/BoletaDetalle.md) | El arreglo puede contener hasta 99 objetos. |
| **TotalValorVentaOpeGravada**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Gravado, sin el "descuento global" (si es que tiene), y sin el "Subtotal de Anticipo" (si es que tiene). | decimal(14,2) |
| **TotalValorVentaOpeInafecta**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Inafecto, sin el "descuento global" (si es que tiene), y sin el "Subtotal de Anticipo" (si es que tiene). | decimal(14,2) |
| **TotalValorVentaOpeExonerada**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Exonerado, sin el "descuento global" (si es que tiene), y sin el "Subtotal de Anticipo" (si es que tiene). | decimal(14,2) |
| **TotalValorVentaOpeGratuita**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Gratuito. | decimal(14,2) |
| **PorcentajeDescuentoGlobal**  <br>`opcional`  <br>`number` | Porcentaje global de descuento de la venta, expresdo en formato decimal: 15 % equivale a _0.15_ | decimal(14,2) |
| **ImporteDescuentoGlobal**  <br>`opcional`  <br>`number` | Importe del descuento global de la venta sin incluir el impuesto correspondiente. | decimal(14,2) |
| **ImporteDescuentoGlobalConIgv**  <br>`opcional`  <br>`number` | Importe del descuento global de la venta incluyendo el impuesto correspondiente. |  |
| **Igv**  <br>`obligatorio`  <br>`number` | Monto total del IGV de la venta. Calculado en base a los "Totales de Valor Venta", con el "Descuento Global sin IGV" (si es que tiene). | decimal(14,2) |
| **ImporteTotal**  <br>`obligatorio`  <br>`number` | Importe total de la venta. Calculado en base a los "Totales de Valor Venta", menos el "Descuento Global" (si es que tiene), más el "IGV", menos el "Total de Anticipo" (si es que tiene) | decimal(14,2) |
| **AnticipoBoleta**  <br>`opcional`  <br>`array` | [[Ver objeto]](../EntidadBoleta/BoletaAnticipo.md) |  |
| **TotalAnticipos**  <br>opcional  <br>number | Sumatoria de los importes totales de anticipos (incluye los impuestos). | decimal(14, 2) |
| **SubtotalAnticipos**  <br>opcional  <br>number | Sumatoria de los valores de venta de anticipos (no incluye los impuestos). | decimal(14, 2) |

·

**CONDICIONES Y VALIDACIONES DE LOS TOTALES DE LA BOLETA**

_**Por ítem:**_

| Campos | Comentarios |
| --- | --- |
| Valor Venta del ítem | El cálculo del valor venta es igual a la cantidad por el valor unitario (precio sin IGV).  <br>_**Fórmula:**_ Cantidad × ValorUnitario. |
| Precio unitario del ítem | El cálculo del precio unitario es igual al valor unitario más el porcentaje de IGV del ítem de la venta.  <br>_**Fórmula:**_ ValorUnitario × (1 + PorcentajeIgv ÷ 100)  <br>_**Validación:**_ La diferencia absoluta entre el precio unitario calculado por PecanoFact y el precio unitario ingresado por el usuario no debe excede de 0.5 |
| IGV del ítem | El cálculo del IGV es igual al valor venta aplicándole el porcentaje de IGV del ítem de la venta.  <br>_**Fórmula:**_ ValorVenta × (PorcentajeIgv ÷ 100)  <br>_**Validación:**_ La diferencia absoluta entre el IGV calculado por PecanoFact y el IGV ingresado por el usuario no debe exceder de 0.5 |
| Total del ítem | El cálculo del total es igual al valor venta más el IGV del ítem de la venta.  <br>_**Fórmula:**_ ValorVenta + IGV  <br>_**Validación:**_ La diferencia absoluta entre el total calculado por PecanoFact y el total ingresado por el usuario no debe exceder de 0.5 |

·

_**Por cabecera:**_

| Campos | Comentarios |
| --- | --- |
| Valor venta general de operaciones gravadas | La diferencia absoluta entre el total de valor venta calculado por PecanoFact y el total de valor venta ingresado por el usuario no debe exceder de 0.5 |
| Valor venta general de operaciones inafectas | La diferencia absoluta entre el total de valor venta calculado por PecanoFact y el total de valor venta ingresado por el usuario no debe exceder de 0.5 |
| Valor venta general de operaciones exoneradas | La diferencia absoluta entre el total de valor venta calculado por PecanoFact y el total de valor venta ingresado por el usuario no debe exceder de 0.5 |
| IGV general | La diferencia absoluta entre el total del IGV calculado por PecanoFact y el total del IGV ingresado por el usuario no debe exceder de 0.5 |
| Total general | La diferencia absoluta entre el importe total calculado por PecanoFact y el importe total ingresado por el usuario no debe exceder de 0.5 |