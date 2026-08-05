### NotaDebitoDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número secuencial del ítem dentro del detalle de la nota de débito. | Valor mínimo 1.  <br>Valor máximo 99. |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del producto/servicio. | Entre 1 y 3 caracteres. |
| **UnidadMedidaAlias**  <br>`opcional`  <br>`string` | Unidad de medida alternativa del producto/servicio. Si el usuario lo deja en blanco, obtiene el código de la unidad de medida establecida por la SUNAT.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 35 caracteres. |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del producto/servicio. | decimal(20,10). |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del producto/servicio. | Máximo 30 caracteres. |
| **CodigoProductoGTIN**  <br>`opcional`  <br>`string` | Código del producto GTIN es un número global definido por GS1 que identifica de manera única un producto/servicio comercial.  <br>Por ejemplo: 7751234567890  <br>  - 775: Prefijo GS1 (Perú).  <br>  - 1234: Empresa.  <br>  - 56789: Producto.  <br>  - 0: Dígito control. | Conformado, según el tipo de estructura GTIN:  <br>  - 8 dígitos, para "GTIN-8".  <br>  - 12 dígitos, para "GTIN-12".  <br>  - 13 dígitos, para "GTIN-13".  <br>  - 14 dígitos, para "GTIN-14".  |
| **CodigoProductoSunat**  <br>`opcional`  <br>`string` | Código del producto SUNAT que clasifica a los productos/servicios según el estándar internacional UNSPSC para categorizarlos de manera uniforme.  <br>Por ejemplo: 50202306  <br>  - 50: Segmento: Alimentos, bebidas y tabaco.  <br>  - 20: Familia: Bebidas.  <br>  - 23: Clase: Bebidas no alcohólicas.  <br>  - 06: Producto: Refrescos. | Conformado por 8 dígitos.  <br>Referencia: Catálogo 25. |
| **DescripcionProducto**  <br>`obligatorio`  <br>`string` | Descripción del producto/servicio.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 500 caracteres. |
| **DetalleLoteProducto**  <br>`opcional`  <br>`array` | Lotes del producto por cada detalle del comprobante.  <br>[[Ver objeto]](../Entidad/LoteProducto.md) |  |
| **ValorUnitario**  <br>`obligatorio`  <br>`number` | Precio del producto/servicio sin IGV. Consignar indicar la mayor cantidad en la parte de decimal para que ayuden a la validación de calculos. | decimal(20,10). |
| **PrecioUnitario**  <br>`obligatorio`  <br>`number` | Precio de venta unitario por ítem (inc. IGV) | decimal(20,10). |
| **Igv**  <br>`obligatorio`  <br>`number` | Valor del IGV del ítem. | decimal(20,2). |
| **PorcentajeIgv**  <br>`obligatorio`  <br>`number` | Porcentaje del IGV del item. Debe ser expresado en formato entero.  <br>**Ejemplo:** 18. |  |
| **TipoAfectacionIgv**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoAfectacionIgv.md) |  |
| **ValorVenta**  <br>`obligatorio`  <br>`number` | Valor venta del item. Es la multiplicación de **Cantidad** por **ValorUnitario**. | decimal(20,2). |
| **Total**  <br>`obligatorio`  <br>`number` | Total del item. | .decimal(20,2). |