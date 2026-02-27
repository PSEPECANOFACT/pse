### OtroDocumentoRelacionado

| **Propiedad** | **Descripción** | **Condición** |
| - | - | - |
| IdItem  <br>`obligatorio`  <br>`number` | Numero de ítem de otros documentos relacionados. | Debe estar comprendido entre 1 y 99. |
| TipoOtroDocumentoRelacionado  <br>`obligatorio`  <br>`number` | Tipo del documento relacionado al comprobante.  <br>[[Ver listado]](../Listado/TipoComprobanteRelacionadoOtro.md) | Valores para Factura:  <br>2, 3, 4, 5, 6, 7, 8, 9 y 99. |
| NumeroOtroDocumentoRelacionado  <br>`obligatorio`  <br>`string` | Número del documento relacionado al comprobante. | Máximo de caracteres: 30.  <br>No se permite espacios, saltos de línea, tab, etc. |