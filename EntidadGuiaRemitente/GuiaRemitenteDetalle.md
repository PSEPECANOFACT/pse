### GuiaRemitenteDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de orden del ítem. | Caracteres numéricos de hasta 4 dígitos (numeración secuencial). |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del bien. | decimal(20,10) |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del bien. | Alfanumérico de 1 a 3 caracteres. Solo letras mayúsculas y números.  <br>Si el motivo de traslado es "Exportación" o "Importación", se debe consignar la unidad de medida para DAM y DS (Catálogo 65), sino consignar la unidad de medida comercial (Catálogo 03). |
| **UnidadMedidaAlias**  <br>`opcional`  <br>`string` | Nombre, descripción o abreviatura alternativa de la unidad de medida del bien.  <br>Dato opcional solo para mostrarlo en la representación impresa.  <br>Si no se ingresa ningún valor, tomará automáticamente el valor del campo "UnidadMedida".  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Alfanumérico de hasta 35 caracteres. |
| **Descripcion**  <br>`obligatorio`  <br>`string` | Descripción detallada del bien.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Alfanumérico de 3 a 500 caracteres. |
| **DetalleLoteProducto**  <br>`opcional`  <br>`array` | Lotes del producto por cada detalle del comprobante.  <br>[[Ver objeto]](../Entidad/LoteProducto.md) |  |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del bien. | Alfanumérico de hasta 30 caracteres. |
| **CodigoProductoSunat**  <br>`condicional`  <br>`string` | Código del producto SUNAT que clasifica a los productos/servicios según el estándar internacional UNSPSC para categorizarlos de manera uniforme.  <br>Por ejemplo: 50202306  <br>  - 50: Segmento: Alimentos, bebidas y tabaco.  <br>  - 20: Familia: Bebidas.  <br>  - 23: Clase: Bebidas no alcohólicas.  <br>  - 06: Producto: Refrescos. | Conformado por 8 dígitos.  <br>Referencia: Catálogo 25. |