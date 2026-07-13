### Buscar por rango de fechas

Realiza una consulta para obtener el estado de los comprobantes según un rango de fechas, **pero las fechas proporcionadas deben pertener al mismo mes**.

A continuación, se indica el enpoint para realizar esta consulta:

| **Endpoint** | **Método** |
| --- | --- |
| {base_url}**/api/v2/cpe/consulta/estado/rangofecha** | POST |

Al igual que con la generación del CPE, en la consulta del estado del CPE se necesita también un Token utilizable:

| **Headers** |  |
| --- | --- |
| TOKEN-PSE-PECANOFACT | TOKEN-GENERADO |

Para esta acción, se debe generar un nuevo Token, en caso haya superado el tiempo de vida de 1 hora.

#### Solicitud:

En el siguiente cuadro se detallan las propiedades que se deben enviar en el cuerpo de la solicitud:

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **TipoDocumento**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoComprobante.md) |  |
| **FechaInicio**  <br>`obligatorio`  <br>`string` | Fecha inicio del rango.  <br>**Ejemplo:**  <br>yyyy-MM-dd |  |
| **FechaFin**  <br>`obligatorio`  <br>`string` | Fecha fin del rango:  <br>**Ejemplo:**  <br>yyyy-MM-dd | La **fecha fin**, debe pertencer al mismo mes de la **fecha de inicio**. |

#### Código de respuesta Http 200:

Si el código de la respuesta es **200**, significa que la solicitud enviada cumplió con los requísitos mínimos para obtener información de los documentos generados en ese rango de fechas. A continuación, se explica la respuesta obtenida:

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **TipoDocumento**  <br>`number` | [[Ver listado]](../Listado/TipoComprobante.md) |  |
| **FechaEmision**  <br>`string` | Fecha de emisión del comprobante.  <br>**Ejemplo:**  <br>yyyy-MM-dd |  |
| **NumeroDocumento**  <br>`string` | Serie y correlativo del comprobante.  <br>Formato: [Serie]-[Correlativo] | 13 caracteres  <br>Serie: 4 caracteres  <br>Separador: Guion  <br>Correlativo: 8 dígitos |
| **EstadoDocumento**  <br>`number` | [[Ver listado]](../Listado/EstadoDocumento.md) |  |
| **DescripcionCdrDeclaracion**  <br>`string` | Mensaje informativo sobre la descripción del CDR |  |
| **IdentificadorAnulacion**  <br>`string` | Identificador del resumen diario (RC) o comunicación de baja (RA) que anuló el comprobante. | Si **EstadoDocumento** es **Anulado,** esta propiedad debe tener valor; de lo contrario, será nulo. |
| **DescripcionCdrAnulacion**  <br>`string` | Mensaje informativo sobre la descripción del CDR |  |

Ejemplo de una respuesta válida:

<img src="https://content.pstmn.io/163fcc26-826d-4102-b8cd-7572c17990ff/aW1hZ2UucG5n" width="1336" height="566">

#### Código de respuesta Http 400:

Si el código de la respuesta es **400**, se trata que la solicitud enviada no cumple con la estructura requerida o una validación controlada por el PSE. El usuario debe revisar el **'MensajeError'** proporcionado por el servicio para interpretar el mensaje y corregirlo en la siguiente petición.

| **Response** |
| --- |
| {  <br>"CodigoError": "0",  <br>"MensajeError": "_Mensaje de error controlado_"  <br>} |

Ejemplo del código de respuesta 400:

<img src="https://content.pstmn.io/040c6947-d25d-4d61-b7fd-97d6fa6e2355/aW1hZ2UucG5n" width="1333" height="375">

#### Código de respuesta Http 404:

Si el código de respuesta es **404**, indica que la solicitud enviada cumple con la estructura requerida. Sin embargo, no se encontró alguna coincidencia en la búsqueda.

| **Response** |
| --- |
| {  <br>"CodigoError": "0",  <br>"MensajeError": "_Mensaje informativo de búsqueda_"  <br>} |

Ejemplo del código de respuesta 404:

<img src="https://content.pstmn.io/57c01d5e-8278-43c5-a354-a748c2457433/aW1hZ2UucG5n" width="987" height="430">

#### Código de respuesta Http 500:

Si el código de respuesta es **500**, indica un error no controlado por el PSE, proveniente de alguna parte del servicio. En este caso, por temas de seguridad el servicio no proporcionará el mensaje detallado del error, solo el código, que será distinto de cero (0).

| **Reponse** |
| --- |
| {  <br>"CodigoError": "1511592815",  <br>"MensajeError": null  <br>} |

Ante este escenario, el usuario deberá reportarlo a los canales definidos en el acuerdo comercial, o por los mecanismos otorgados por la empresa, para que el error pueda ser aclarado o, en su defecto, resuelto.

Ejemplo del código de respuesta 500:

<img src="https://content.pstmn.io/fa78cfa0-570d-4919-9605-17cd36cd1196/aW1hZ2UucG5n" width="888" height="222">