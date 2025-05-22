### ResumenDiarioDetalle

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de fila. | Número entero.  <br>Máximo: 100 ítems. |
| **TipoDocumento**  <br>`obligatorio`  <br>`number` | Tipo de comprobante del documento 'Boleta de Venta', 'Nota de Crédito' o 'Nota de Débito'.  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Solo 20, 30 o 40. |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y número de correlativo del documento 'Boleta de Venta', 'Nota de Crédito' o 'Nota de Débito'. |  |
| **Adquiriente**  <br>`condicional`  <br>`object` | Datos del adquiriente o usuario.  <br>[[Ver entidad]](../Entidad/Adquiriente2.md) | Es obligatorio si el valor de 'ImporteTotalVenta' es mayor que 700. |
| **CodigoOperacion**  <br>`obligatorio`  <br>`number` | Código de operación o de estado del ítem (Resumen Diario).  <br>[[Ver listado]](../Listado/CodigoEstadoResumenDiario.md) | Número entero. |
| **TipoDocumentoQueModifica**  <br>`condicional`  <br>`number` | Tipo de documento que modifica (comprobante de referencia 'Boleta de Venta' (20)).  <br>[[Ver listado]](../Listado/TipoComprobante.md) | Solo se debe consignar cuando 'TipoDocumento' es "Nota de Crédito" (30) o "Nota de Débito" (40). |
| **NumeroDocumentoQueModifica**  <br>`condicional`  <br>`string` | Número de documento que modifica (comprobante de referencia 'Boleta de Venta' (20)). | Solo se debe consignar cuando 'TipoDocumento' es "Nota de Crédito" (30) o "Nota de Débito" (40). |
| **TipoMoneda**  <br>`obligatorio`  <br>`number` | Tipo de moneda del comprobante.  <br>[[Ver listado]](../Listado/TipoMoneda.md) | 1: Soles.  <br>2: Dólares. |
| **TotalValorVentaOperacionesGravadas**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones gravadas. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalValorVentaOperacionesExoneradas**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones exoneradas. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalValorVentaOperacionesInafectas**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones inafectas. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalValorVentaOperacionesGratuitas**  <br>`condicional`  <br>`number` | Total valor de venta de operaciones gratuitas. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalOtrosCargos**  <br>`condicional`  <br>`number` | Importe total de otros cargos del ítem. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalIgv**  <br>`condicional`  <br>`number` | Total IGV.  <br>**Nota:** Solo se puede consignar un valor mayor que cero en 'TotalIgv' o en 'TotalIvap', pero no en ambos. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalIvap**  <br>`condicional`  <br>`number` | Total IVAP.  <br>**Nota:** Solo se puede consignar un valor mayor que cero en 'TotalIgv' o en 'TotalIvap', pero no en ambos. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalIsc**  <br>`condicional`  <br>`number` | Total ISC. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **TotalOtrosTributos**  <br>`condicional`  <br>`number` | Total Otros tributos. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |
| **ImporteTotalVenta**  <br>`condicional`  <br>`number` | Importe total. | Formato: n(12,2)  <br>Si se omite, el valor por defecto es cero (0).  <br>No acepta NULL. |