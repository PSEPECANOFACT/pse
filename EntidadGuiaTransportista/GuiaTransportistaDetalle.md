### GuiaTransportistaDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de orden del ítem. | Caracteres numéricos de hasta 4 dígitos (numeración secuencial). |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del bien. | decimal(20,10) |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del bien. | Alfanumérico de 1 a 3 caracteres. Solo letras mayúsculas y números.  <br>Si el documento relacionado es DAM o DS, se debe consignar la unidad de medida para DAM y DS (Catálogo 65), sino consignar la unidad de medida comercial (Catálogo 03). |
| **UnidadMedidaAlias**  <br>`opcional`  <br>`string` | Nombre, descripción o abreviatura alternativa de la unidad de medida del bien.  <br>Dato opcional solo para mostrarlo en la representación impresa.  <br>Si no se ingresa ningún valor, tomará automáticamente el valor del campo "UnidadMedida".  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Alfanumérico de hasta 35 caracteres. |
| **Descripcion**  <br>`obligatorio`  <br>`string` | Descripción detallada del bien.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Alfanumérico de 3 a 500 caracteres. |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del bien. | Alfanumérico de hasta 30 caracteres. |
| **CodigoProductoSunat**  <br>`condicional`  <br>`string` | Código de Producto SUNAT. | Caracteres numéricos de hasta 8 dígitos. |