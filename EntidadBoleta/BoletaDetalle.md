### BoletaDetalle

| Propiedad | Descripción | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número secuencial del ítem dentro del detalle del comprobante. | Valor mínimo: 1.  <br>Valor máximo: 99. |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del producto/servicio | Máximo 30 caracteres. |
| **Descripcion**  <br>`obligatorio`  <br>`string` | Descripción del producto/servicio.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 500 caracteres. |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del producto/servicio. | Entre 1 y 3 caracteres. |
| **UnidadMedidaAlias**  <br>`opcional`  <br>`string` | Unidad de medida alternativa del producto/servicio. Si el usuario lo deja en blanco, obtiene el código de la unidad de medida establecida por la SUNAT.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 35 caracteres. |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del producto/servicio. | decimal(20,10) |
| **ValorUnitario**  <br>`obligatorio`  <br>`number` | Permite el ingreso del 'Valor unitario' del producto por ítem (para operaciones onerosas) o del 'Valor referencial unitario' del producto por ítem (para operaciones no onerosas/gratuitas). En ambos casos, el valor es sin IGV, y no debe ser afectado por el descuento por ítem.  <br>Es preferible enviar la mayor cantidad de decimales para hacer más preciso la validación de cálculos.  <br>_Por ejemplo:_  <br>**_ValorUnitario = 10.593220339_**  <br>**_PorcentajeDescuento = 0.05_**  <br>**_PrecioUnitario = 11.875_** (valor unitario con IGV (12.50) y aplicándole el descuento del 5 %)  <br>_(*) Para mayor detalle revisar el ejemplo práctico de una venta con descuento por ítem en la parte inferior del documento._  | decimal(20,10) |
| **PrecioUnitario**  <br>`obligatorio`  <br>`number` | Precio del producto/servicio incluido el IGV. En caso se trabaje con descuento por ítem, el valor del precio debe incluir dicho descuento.  <br>Si el tipo de afectación es gratuito, consignar cero (0). <br>_Por ejemplo:_  <br>**_ValorUnitario = 10.593220339_**  <br>**_PorcentajeDescuento = 0.05_**  <br>**_PrecioUnitario = 11.875_** (valor unitario con IGV (12.50) y aplicándole el descuento del 5 %)  <br>_(*) Para mayor detalle revisar el ejemplo práctico de una venta con descuento por ítem en la parte inferior del documento._  | decimal(20,10) |
| **TipoAfectacionIgv**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoAfectacionIgv.md) |  |
| **PorcentajeDescuento**  <br>`opcional`  <br>`number` | Porcentaje de descuento del ítem, expresado en formato decimal (por ejemplo: 0.05 que representa el 5 %). | decimal(8, 3) |
| **ImporteDescuento**  <br>`opcional`  <br>`number` | Importe del descuento basado en el valor venta del item 'antes' de los impuestos.  <br>_Por ejemplo:_  <br>**_Cantidad = 3_**  <br>**_ValorUnitario = 10.593220339_**  <br>**_PorcentajeDescuento = 0.05_**  <br>**_ImporteDescuento = 1.59_**  (cantidad por valor unitario aplicándole el porcentaje de descuento)  <br>_(*) Para mayor detalle revisar el ejemplo práctico de una venta con descuento por ítem en la parte inferior del documento._  | decimal(14, 2) |
| **PorcentajeIgv**  <br>`obligatorio`  <br>`number` | Porcentaje del IGV del item. Debe ser expresado en formato entero.  <br>**Ejemplo:**  <br>18 (para 18 %) |  |
| **ValorVenta**  <br>`obligatorio`  <br>`number` | Valor venta del item. Es la multiplicación de **Cantidad** por **ValorUnitario**, incluido el "descuento por ítem" (si es que tiene).  <br>_(*) Para mayor detalle revisar el ejemplo práctico de una venta con descuento por ítem en la parte inferior del documento._  | decimal(20,2) |
| **Igv**  <br>`obligatorio`  <br>`number` | Valor del IGV del ítem, incluido el "descuento por ítem" (si es que tiene). <br>_(*) Para mayor detalle revisar el ejemplo práctico de una venta con descuento por ítem en la parte inferior del documento._ | decimal(20,2) |
| **Total**  <br>`obligatorio`  <br>`number` | Total del item. | decimal(20,2) |

**Ejemplo práctico de una venta con descuento por ítem:**

| Campo | Valor | Fórmula |
| --- | --- | --- |
| Cantidad | 3 | |
| ValorUnitario  <br>_(sin descuento)_ | 10.5932203390 |  |
| PrecioUnitario  <br>_(con descuento)_ | 11.88 | = ValorUnitario * (1 + PorcentajeIgv / 100) * (1 - PorcentajeDescuento) |
| PorcentajeDescuento | **0.05** | |
| ImporteDescuento | 1.59 | = Redondear(Cantidad * ValorUnitario * PorcentajeDescuento, 2) |
| PorcentajeIgv | **18** | |
| ValorVenta | 30.19 | = Redondear(Cantidad * ValorUnitario * (1 - PorcentajeDescuento), 2) |
| Igv | 5.43 | = Redondear(ValorVenta * PorcentajeIgv / 100, 2) |
| Total | 35.62 | = Redondear(ValorVenta + Igv, 2) |

**NOTA:**
* Si la venta no es Gravada, el valor de "PorcentajeIgv" debe ser igual a cero (0).  <br>
* Si la venta no tiene Descuentos por ítem, el valor de "PorcentajeDescuento" debe ser igual a cero (0); por lo tanto, el valor de "ImporteDescuento" también debe ser igual a cero (0).