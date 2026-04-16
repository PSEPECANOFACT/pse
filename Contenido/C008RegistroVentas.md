### Registro de ventas

Realiza una consulta para obtener el registr de venas de los comprobantes según fechas, documento de identidad, tipo de comprobante, moneda y estado.

A continuación, se indica el enpoint para realizar esta consulta:

| **Endpoint** | **Método** |
| --- | --- |
| {base_url}**/api/v2/cpe/consulta/cpe/registroventas** | POST |

Al igual que con la generación del CPE, en la consulta del registro de ventas de los CPE se necesita también un Token utilizable:

| **Headers** |  |
| --- | --- |
| TOKEN-PSE-PECANOFACT | TOKEN-GENERADO |

Para esta acción, se debe generar un nuevo Token, en caso haya superado el tiempo de vida de 1 hora.

#### Solicitud:

En el siguiente cuadro se detallan las propiedades que se deben enviar en el cuerpo de la solicitud:

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **FechaInicio**  <br>`obligatorio`  <br>`string` | Fecha de emisión inicial de los CPE.  <br>**Ejemplo:** "2025-09-01" | Formato: "yyyy-MM-dd".  <br>La fecha de inicio debe ser menor o igual a la fecha de fin. |
| **FechaFin**  <br>`obligatorio`  <br>`string` | Fecha de emisión final de los CPE.  <br>**Ejemplo:** "2025-09-30" | Formato: "yyyy-MM-dd". |
| **TipoDocumentoIdentidad**  <br>`opcional`  <br>`number` | Tipo de documento de identidad del adquiriente.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md) |  |
| **NumeroDocumentoIdentidad**  <br>`condicional`  <br>`string` | Número de documento de identidad del adquiriente. | Si el tipo de DI es DNI, 8 dígitos. Si es RUC, 11 dígitos. si es otro tipo, máximo 20 caracteres.  <br>Si no se consigna el tipo DI, tampoco se debe consignar el número de DI. |
| **RazonSocial**  <br>`opcional`  <br>`string` | Razón social del adquiriente. |  |
| **TipoComprobante**  <br>`opcional`  <br>`number` | Tipo de comprobante o documento.  <br>[[Ver listado]](../Listado/TipoComprobante.md) |  |
| **Serie**  <br>`condicional`  <br>`string` | Serie del número de comprobante.  <br>Ejemplo: "FF15" | Son los 4 primeros caracteres alfanuméricos del número de documento o comprobante.  <br>Si no se consigna el tipo de comprobante, tampoco se debe consignar la serie. |
| **Correlativo**  <br>`condicional`  <br>`number` | Número correlativo del comprobante.  <br>Ejemplo: 1500 | El correlativo debe ser mayor que cero, y comprender entre 1 y 99999999.  <br>Si no se consigna la serie del comprobant, tampoco se debe consignar el correlativo. |
| **TipoMoneda**  <br>`opcional`  <br>`number` | Tipo de moneda del comprobante.  <br>[[Ver listado]](../Listado/TipoMoneda.md) |  |
| **EstadoDocumento**  <br>`opcional`  <br>`number` | Estado actual del documento. | 1: EMITIDO.  <br>2: ANULADO. |

#### Código de respuesta Http 200:

Si el código de la respuesta es **200**, significa que la solicitud enviada cumplió con los requísitos mínimos para obtener información del registro de ventas. A continuación, se explica la respuesta obtenida:

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **FechaEmision**  <br>`string` | Fecha de emisión del CPE. |  |
| **FechaVencimiento**  <br>`string` | Fecha de vencimiento del CPE. | Si la condición es contado, el valor es _NULL_. |
| **Moneda**  <br>`string` | Moneda del CPE. | Puede ser "PEN" o "USD". |
| **TipoDoc**  <br>`string` | Código SUNAT del tipo de documento del CPE.  <br>_(Catálogo 01)_ | Los valores pueden ser: "01" (Factura), "03" (Boleta de venta), "07" (Nota de crédito) o "08" (Nota de débito). |
| **Documento**  <br>`string` | Nombre del tipo de documento del CPE. | Los valores pueden ser: "Factura", "Boleta de venta", "Nota de crédito" o "Nota de débito". |
| **SerieNumero**  <br>`string` | Número del documento del CPE (serie y correlativo). | Formato: XXXX-12345678 |
| **TipoDi**  <br>`string` | Código SUNAT del tipo de documento de identidad del adquiriente.  <br>_(Catálogo 06)_ | Ejemplo: "1" (DNI), "6" (RUC), etc. |
| **NumeroDi**  <br>`string` | Número del documento de identidad del adquiriente. | Si es DNI, 8 dígitos; si es RUC, 11 dígitos; si son otros, hasta 20 caracteres. |
| **Cliente**  <br>`string` | Nombre o razón social del adquiriente. | Caracteres alfanuméricos. |
| **OpGravadas**  <br>`number` | Total valor venta de operaciones gravadas onerosas. | Valor por defecto: 0 |
| **OpExoneradas**  <br>`number` | Total valor venta de operaciones exoneradas onerosas. | Valor por defecto: 0 |
| **OpInafectas**  <br>`number` | Total valor venta de operaciones inafectas. | Valor por defecto: 0 |
| **OpGratuitas**  <br>`number` | Total valor venta de operaciones gratuitas. | Valor por defecto: 0 |
| **OpExportacion**  <br>`number` | Total valor venta de operaciones exportadas. | Valor por defecto: 0 |
| **Descuentos**  <br>`number` | Descuento global del CPE. | Valor por defecto: 0 |
| **Igv**  <br>`number` | IGV (Impuesto General a las Ventas) del CPE. | Valor por defecto: 0 |
| **Isc**  <br>`number` | ISC (Impuesto Selectivo al Consumo) del CPE. | Valor por defecto: 0 |
| **Ivap**  <br>`number` | IVAP (Impuesto a la Venta Arroz Pilado) del CPE. | Valor por defecto: 0 |
| **OtrosImpuestos**  <br>`number` | Otros impuestos. | Valor por defecto: 0 |
| **OtrosCargos**  <br>`number` | Otros cargos. | Valor por defecto: 0 |
| **Icbper**  <br>`number` | ICBPER (Impuesto al Consumo de Bolsas de Plástico en el Perú) del CPE. | Valor por defecto: 0 |
| **ImporteTotal**  <br>`number` | Importe total del CPE. | Valor por defecto: 0 |
| **EstadoDoc**  <br>`string` | Estado actual del CPE. | Los valores posibles son: "EMITIDO", "ANULADO". |
| **ResumenDiario**  <br>`string` | Indica si el CPE está asociado a un Resumen Diario. | Los valores son: "Sí" o "No".  <br>En el caso de las 'Facturas' y 'Notas de crédito o débito' de facturas, su valor constante es "No". Para el caso de las 'Boletas' y 'Notas de crédito o débito' de boletas, su valor depende de la asociación. |
| **IdentificadorResumenDiario**  <br>`string` | Número de identificador del Resumen Diario. | Para el caso de 'Facturas' o 'Notas de crédito o débito' de facturas, su valor constante es _null_. Para el caso de 'Boletas' o 'Notas de crédito o débito' de boletas, su valor depende de la asociación. |
| **EstadoDocTributarioOse**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **EstadoDocTributarioSunat**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **DocRefFechaEmision**  <br>`string` | Fecha de emisión del documento de referencia o que modifica. | Este campo debe tener valor solo para los CPE "Nota de crédito" y "Nota de débito". Para "Factura" y "Boleta de venta", su valor constantes es _null_. |
| **DocRefTipoDoc**  <br>`string` | Código SUNAT del tipo de documento de referencia o que modifica. | Este campo debe tener valor solo para los CPE "Nota de crédito" y "Nota de débito". Para "Factura" y "Boleta de venta", su valor constantes es _null_. |
| **NomDocRefTipoDoc**  <br>`string` | Nombre del documento de referencia o que modifica. | Este campo debe tener valor solo para los CPE "Nota de crédito" y "Nota de débito". Para "Factura" y "Boleta de venta", su valor constantes es _null_. |
| **DocumentoReferencia**  <br>`string` | Número del documento de referencia o que modifica. | Este campo debe tener valor solo para los CPE "Nota de crédito" y "Nota de débito". Para "Factura" y "Boleta de venta", su valor constantes es _null_. |
| **FechaHoraGeneracionCdrOse**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **FechaHoraGeneracionArSunat**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **RespuestaOsePecanofact**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **MotivoObservacionOsePecanofact**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **RespuestaSunat**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **MotivoObservacionSunat**  <br>`string` | Solo para OSE. | Valor constante: _null_. |
| **ServicioOrigen**  <br>`string` | Origen de los datos. | Valor constante: "PSE". |

Ejemplo de una respuesta válida:

<img src="https://content.pstmn.io/d30f84bb-5a0b-419f-bb65-c2e800113334/aW1hZ2UucG5n" width="737" height="408">

#### Código de respuesta Http 400:

Si el código de la respuesta es **400**, se trata que la solicitud enviada no cumple con la estructura requerida o una validación controlada por el PSE. El usuario debe revisar el **'MensajeError'** proporcionado por el servicio para interpretar el mensaje y corregirlo en la siguiente petición.

| **Response** |
| --- |
| {  <br>"CodigoError": "0",  <br>"MensajeError": "_Mensaje de error controlado_"  <br>} |

Ejemplo del código de respuesta 400:

<img src="https://content.pstmn.io/0b75f587-3dc6-492d-9a9f-bc9162c656d4/aW1hZ2UucG5n" width="641" height="312">

#### Código de respuesta Http 404:

Si el código de respuesta es **404**, indica que la solicitud enviada cumple con la estructura requerida. Sin embargo, no se encontró alguna coincidencia en la búsqueda.

| **Response** |
| --- |
| {  <br>"CodigoError": "0",  <br>"MensajeError": "No se encontró información"  <br>} |

Ejemplo del código de respuesta 404:

<img src="https://content.pstmn.io/35f059e8-9ec2-4cd6-b665-984cb7c10d21/aW1hZ2UucG5n" width="550" height="291">

#### Código de respuesta Http 500:

Si el código de respuesta es **500**, indica un error no controlado por el PSE, proveniente de alguna parte del servicio. En este caso, por temas de seguridad el servicio no proporcionará el mensaje detallado del error, solo el código, que será distinto de cero (0).

| **Reponse** |
| --- |
| {  <br>"CodigoError": "1511592815",  <br>"MensajeError": null  <br>} |

Ante este escenario, el usuario deberá reportarlo a los canales definidos en el acuerdo comercial, o por los mecanismos otorgados por la empresa, para que el error pueda ser aclarado o, en su defecto, resuelto.

Ejemplo del código de respuesta 500:

<img src="https://content.pstmn.io/6f5cc58c-fcf7-4d9c-a244-34df11e25b09/aW1hZ2UucG5n" width="540" height="290">