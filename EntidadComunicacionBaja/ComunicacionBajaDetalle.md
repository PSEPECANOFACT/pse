### ComunicacionBajaDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de ítem. | Número entero.  <br>Máximo: 100 ítems. |
| **TipoDocumento**  <br>`obligatorio`  <br>`number` | Tipo de comprobante del documento 'Factura', 'Nota de Crédito' o 'Nota de Débito'.  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Solo 10, 30 o 40. |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y número de correlativo del documento 'Factura', 'Nota de Crédito' o 'Nota de Débito'. |  |
| **MotivoBaja**  <br>`obligatorio`  <br>`string` | Motivo de baja.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Mínimo: 3 caracteres.  <br>Máximo: 100 caracteres. |