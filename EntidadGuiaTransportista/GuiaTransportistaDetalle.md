### GuiaTransportistaDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de orden del ítem. | Caracteres numéricos de hasta 4 dígitos (numeración secuencial). |
| **Cantidad**  <br>`obligatorio`  <br>`number` | Cantidad del bien. | decimal(20,10) |
| **UnidadMedida**  <br>`obligatorio`  <br>`string` | Unidad de medida del bien. | Alfanumérico de 2 a 3 caracteres. Solo letras mayúsculas y números. |
| **Descripcion**  <br>`obligatorio`  <br>`string` | Descripción detallada del bien. | Alfanumérico de 3 a 250 caracteres. |
| **CodigoProducto**  <br>`obligatorio`  <br>`string` | Código del bien. | Alfanumérico de hasta 30 caracteres. |
| **CodigoProductoSunat**  <br>`condicional`  <br>`string` | Código de Producto SUNAT. | Caracteres numéricos de hasta 8 dígitos. |