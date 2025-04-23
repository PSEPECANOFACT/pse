### ResumenReversionDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de ítem. | Número entero.  <br>Máximo: 100 ítems. |
| **TipoDocumento**  <br>`obligatorio`  <br>`number` | Tipo de comprobante del documento 'Comprobante de Retención' o 'Comprobante de Percepción'.  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Solo 90 o 91. |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y número de correlativo del documento 'Comprobante de Retención' o 'Comprobante de Percepción'. |  |
| **MotivoBaja**  <br>`obligatorio`  <br>`string` | Motivo de baja.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Mínimo: 3 caracteres.  <br>Máximo: 100 caracteres. |