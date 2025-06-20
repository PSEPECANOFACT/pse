### FacturaDetalle

| Propiedad | Descripción | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número secuencial del ítem dentro del detalle del comprobante. | Valor mínimo: 1.  <br>Valor máximo: 99. |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del producto/servicio | Máximo 30 caracteres. |
| **Descripcion**  <br>`obligatorio`  <br>`string` | Descripción del producto/servicio.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 500 caracteres. |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del producto/servicio. | Entre 1 y 3 caracteres. |
| **UnidadMedidaAlias**  <br>`opcional`  <br>`string` | Unidad de medida alternativa del producto/servicio. Si el usuario lo deja en blanco, obtiene el código de la unidad de medida establecida por la SUNAT.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 35 caracteres. |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del producto/servicio. | decimal(20,10) |
| **ValorUnitario**  <br>`obligatorio`  <br>`number` | Permite el ingreso del 'Valor unitario' del producto por ítem (para operaciones onerosas) o del 'Valor referencial unitario' del producto por ítem (para operaciones gratuitas). En ambos casos, el precio es sin IGV, y no debe ser afectado por el descuento por ítem.  <br>Es preferible enviar la mayor cantidad de decimales para hacer más preciso la validación de cálculos.  <br>**_ValorUnitario = 10.593220339_**  <br>_PrecioUnitario = 12.50_ (sin descuento)  <br>**_PorcentajeDescuento = 0.05_**  <br>**_PrecioUnitario = 11.875_** (con descuento) | decimal(20,10) |
| **PrecioUnitario**  <br>`obligatorio`  <br>`number` | Precio del producto/servicio incluido el IGV. En caso se trabaje con descuento por ítem, el valor del precio debe incluir dicho descuento.  <br>Si el tipo de afectación es gratuito, consignar cero (0). <br>**_ValorUnitario = 10.593220339_**  <br>_PrecioUnitario = 12.50_ (sin descuento)  <br>**_PorcentajeDescuento = 0.05_**  <br>**_PrecioUnitario = 11.875_** (con descuento)| decimal(20,10) |
| **TipoAfectacionIgv**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoAfectacionIgv.md) |  |
| **PorcentajeDescuento**  <br>`opcional`  <br>`number` | Porcentaje de descuento del ítem, expresado en formato decimal (por ejemplo: 0.05). | decimal(8, 3) |
| **ImporteDescuento**  <br>`opcional`  <br>`number` | Importe del descuento basado en el valor venta del item 'antes' de los impuestos. | decimal(14, 2) |
| **PorcentajeIgv**  <br>`obligatorio`  <br>`number` | Porcentaje del IGV del item. Debe ser expresado en formato entero.  <br>**Ejemplo:**  <br>18 (para 18 %) |  |
| **ValorVenta**  <br>`obligatorio`  <br>`number` | Valor venta del item. Es la multiplicación de **Cantidad** por **ValorUnitario**, incluido el "descuento por ítem", si es que tiene. | decimal(20,2) |
| **Igv**  <br>`obligatorio`  <br>`number` | Valor del IGV del ítem, incluido el "descuento por ítem" (si es que tiene). | decimal(20,2) |
| **Total**  <br>`obligatorio`  <br>`number` | Total del item. | decimal(20,2) |

**Ejemplo práctico:**

| Campo | Valor | Fórmula |
| --- | --- | --- |
| precio_unitario_base _(sin descuento)_ | **12.5** | |
| valor_unitario_base _(sin descuento)_ | **10.5932203390** | |
| | | |
| valor_unitario_conDscto _(con descuento)_ | 10.0635593221 | = valor_unitario_base * (1 - PorcentajeDescuento) |
| | | |
| | | |
| | | |
| Cantidad | **3** | |
| ValorUnitario _(sin descuento)_ | 10.5932203390 | = valor_unitario_base |
| PrecioUnitario _(con descuento)_ | 11.875 | = valor_unitario_conDscto * (1 + PorcentajeIgv) |
| PorentajeDescuento | **0.05** | |
| ImporteDescuento | 1.5889830509 | = Cantidad * (ValorUnitario - valor_unitario_conDscto) |
| PorcentajeIgv | **0.18** | |
| ValorVenta | 30.19067797 | = Cantidad * valor_unitario_conDscto |
| Igv | 5.434322034 | = ValorVenta * PorcentajeIgv |
| Total | 35.625 | = ValorVenta + Igv |