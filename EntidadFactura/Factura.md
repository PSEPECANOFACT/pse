### Factura

| Propiedad | Descripción | Condición |
| --- | --- | --- |
| **Emisor**  <br>`obligatorio`  <br>`object` | Datos del emisor.  <br>[[Ver objeto]](../Entidad/Emisor.md) |  |
| **Cliente**  <br>`obligatorio`  <br>`object` | Datos del adquiriente o usuario.  <br>[[Ver objeto]](../Entidad/Adquiriente.md) |  |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo del comprobante.  <br>**Ejemplo:**  <br>F001-00000001 | Máximo 13 caracteres. |
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha y hora de la emisión del comprobante.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **FechaVencimiento**  <br>`obligatorio`  <br>`string` | Fecha y hora del vencimiento del comprobante.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **TipoOperacion**  <br>`obligatorio`  <br>`string` | [[Ver listado]](../Listado/TipoOperacion.md) |  |
| **NumeroOrdenCompra**  <br>`opcional`  <br>`string` | Número de la orden de compra o de servicio. | Máximo hasta 20 caracteres. |
| **DireccionEntregaBien**  <br>`opcional`  <br>`object` | Dirección del lugar en el que se entrega el bien. Dato exclusivo para ventas itinerantes.  <br>[[Ver objeto]](../Entidad/DireccionEntregaBien.md) |  |
| **CodigoPaisUsoServicio**  <br>`opcional`  <br>`string` | Código del pais del uso, explotación o aprovechamiento del servicio. | Debe contener 2 caracteres que representen al país.  <br>En caso el código del país sea consignado, si el tipo de operación es "0201" o "0208", el código no debe ser "PE"; de lo contrario, si el tipo de operación es diferente de "0201" y de "0208", el código del país solo debe ser "PE". |
| **TipoMoneda**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoMoneda.md) |  |
| **TipoCondicionVenta**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoCondicionVenta.md) |  |
| **SubCondicion**  <br>`opcional`  <br>`string` |   <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo hasta 50 caracteres. |
| **FormaPago**  <br>`opcional`  <br>`string` | Aplica sólo a ventas con la condición.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo hasta 50 caracteres. |
| **Correo**  <br>`obligatorio`  <br>`string` | Correos electrónicos de contacto, separados por punto y coma.  <br>**Ejemplo:**  <br>micorreo@midominio.com;tucorreo@tudominio.com | Máximo hasta 5 correos. |
| **ObservacionVenta**  <br>`opcional`  <br>`string` | Observación sobre la venta.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo hasta 100 caracteres. |
| **TipoCambio**  <br>`opcional`  <br>`number` | Tipo de cambio de la operación | Si TipoMoneda es diferente de Soles, este campo se vuelve obligatorio. |
| **MontoNetoPendientePago**  <br>`opcional`  <br>`number` | Monto neto pendiente de pago. Es la sumatoria de todos los montos de las cuotas.  <br>Si el campo se deja en NULL, entonces el valor para el cálculo del monto se obtiene de: 'ImporteTotal' - 'ImporteDetraccion' - 'ImporteRetencion'. | decimal(14, 2)  <br>Este monto debe ser menor o igual que: 'ImporteTotal' - 'ImporteDetraccion' - 'ImportePercepcion'. |
| **DetalleCredito**  <br>`opcional`  <br>`array` | [[Ver objeto]](../Entidad/Credito.md) | Si la condición es al 'Contado', este campo debe ser null. |
| **PlacaVehiculo**  <br>`opcional`  <br>`string` | Número de placa del vehículo automotor. | Máximo 8 caracteres. |
| **DireccionEntrega**  <br>`opcional`  <br>`string` | Dirección de entrega del comprobante de venta.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo: 200 caracteres. |
| **DetalleFactura**  <br>`obligatorio`  <br>`array` | [[Ver entidad]](../EntidadFactura/FacturaDetalle.md) | El arreglo puede contener hasta 99 objetos. |
| **TotalValorVentaOpeGravada**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Gravado, sin el "descuento global" (si es que tiene), y sin el "Subtotal de Anticipo" (si es que tiene). | decimal(14,2) |
| **TotalValorVentaOpeInafecta**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Inafecto, sin el "descuento global" (si es que tiene), y sin el "Subtotal de Anticipo" (si es que tiene). | decimal(14,2) |
| **TotalValorVentaOpeExonerada**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Exonerado, sin el "descuento global" (si es que tiene), y sin el "Subtotal de Anticipo" (si es que tiene). | decimal(14,2) |
| **TotalValorVentaOpeExportada**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Exportación, sin el "descuento global" (si es que tiene), y sin el "Subtotal de Anticipo" (si es que tiene). | decimal(14,2) |
| **TotalValorVentaOpeGratuita**  <br>`opcional`  <br>`number` | Sumatoria del "valor venta del ítem" que tienen el tipo de afectación Gratuito. | decimal(14,2) |
| **PorcentajeDescuentoGlobal**  <br>`opcional`  <br>`number` | Porcentaje global de descuento de la venta, expresdo en formato decimal: 15 % equivale a _0.15_ | decimal(14,2) |
| **ImporteDescuentoGlobal**  <br>`opcional`  <br>`number` | Importe del descuento global de la venta sin incluir el impuesto correspondiente. | decimal(14,2) |
| **ImporteDescuentoGlobalConIgv**  <br>`opcional`  <br>`number` | Importe del descuento global de la venta incluyendo el impuesto correspondiente (el impuesto solo es de las operaciones gravadas). |  |
| **Igv**  <br>`obligatorio`  <br>`number` | Monto total del IGV de la venta. Calculado en base a los "Totales de Valor Venta" de las operaciones gravadas onerosas, con el "Descuento Global sin IGV" (si es que tiene). | decimal(14,2) |
| **IgvGratuito**  <br>`obligatorio`  <br>`number` | Monto total del IGV de la venta de operaciones gratuitas. Calculado en base a los "Totales de Valor Venta" de las operaciones gravadas gratuitas. | decimal(14,2) |
| **ImporteTotal**  <br>`obligatorio`  <br>`number` | Importe total de la venta. Calculado en base a los "Totales de Valor Venta", menos el "Descuento Global" (si es que tiene), más el "IGV", menos el "Total de Anticipo" (si es que tiene) | decimal(14,2) |
| **AnticipoFactura**  <br>`opcional`  <br>`array` | [[Ver objeto]](../EntidadFactura/FacturaAnticipo.md) |  |
| **TotalAnticipos**  <br>`opcional`  <br>`number` | Sumatoria de los importes totales de anticipos (incluye los impuestos). | decimal(14, 2) |
| **SubtotalAnticipos**  <br>`opcional`  <br>`number` | Sumatoria de los valores de venta de anticipos (no incluye los impuestos). | decimal(14, 2) |
| **BienServicioDetraccion**  <br>`opcional`  <br>`number` | [[Ver listado]](../Listado/BienesYServiciosDetracciones.md) | Listado de bienes y servicios sujetos a detracciones. |
| **NumeroCuentaBNDetraccion**  <br>`opcional`  <br>`string` | Numero de cuenta en el Banco de la Nación para la detraccion. Puede incluir números, guiones y espacios en blanco. | Máximo: 100 caracteres. |
| **ImporteDetraccion**  <br>`opcional`  <br>`number` | Monto total de la detracción en la moneda de la transacción (venta). | decimal(14, 2) |
| **ImporteDetraccionEnMN**  <br>`opcional`  <br>`number` | Monto total de la detracción en moneda nacional (PEN). | decimal(14, 2) |
| **PorcentajeDetraccion**  <br>`opcional`  <br>`number` | Porcentaje de la detracción expresado en formato decimal (por ejemplo: 0.10). | decimal(8, 3) |
| **ImporteRetencion**  <br>`opcional`  <br>`number` | Monto total de la retención. | decimal(14, 2) |
| **PorcentajeRetencion**  <br>`opcional`  <br>`number` | Porcentaje de la retencion expresado en formato decimal (por ejemplo: 0.03). | decimal(8, 3) |
| **RegimenPercepcion**  <br>`opcional`  <br>`number` | Identificador del régimen de percepción, del cual se obtiene el porcentaje de percepción.  <br>[[Ver listado]](../Listado/RegimenPercepcion.md) | Número entero. |
| **ImportePercepcion**  <br>`opcional`  <br>`number` | Importe percibido. Es el importe obtenido de la 'Base Imponible de la Percepción' por el 'Porcentaje de percepción' (según el 'Regimen de Percepción' seleccionado), en moneda nacional. | decimal(14, 2) |
| **BaseImponiblePercepcion**  <br>`opcional`  <br>`number` | Base imponible de la percepción. | decimal(14, 2)  <br>Este monto debe ser menor o igual que 'ImporteTotal' en moneda nacional. |
| **InformacionAdicional**  <br>`opcional`  <br>`array` | Información adicional del comprobante que puede ir en el PDF, en el XML, o en ambos.  <br>[[Ver objeto]](../Entidad/InformacionAdicional.md) |  |

·

**CONDICIONES Y VALIDACIONES DE LOS TOTALES DE LA FACTURA**

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