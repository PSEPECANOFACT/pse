### Obtener enlace PDF por documento

Realiza una consulta para obtener un enlace público para poder visualizar el PDF del comprobante.

A continuación, se indica el enpoint para realizar esta consulta:

| **Endpoint** | **Método** |
| --- | --- |
| {base_url}**/api/v2/cpe/consulta/enlace/pdf** | POST |

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
| **FechaEmision**  <br>`obligatorio`  <br>`string` | Fecha de emisión del comprobante.  <br>**Ejemplo:**  <br>yyyy-MM-dd |  |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo del comprobante.  <br>Formato: \[Serie\]-\[Correlativo\] | 13 caracteres  <br>Serie: 4 caracteres  <br>Separador: Guión  <br>Correlativo: 8 dígitos |

#### Código de respuesta Http 200:

Si el código de la respuesta es **200**, significa que la solicitud enviada cumplió con los requísitos mínimos para obtener información del comprobante. A continuación, se explica la respuesta obtenida:

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **EnlacePDF**  <br>`string` | Link del PDF |  |

Ejemplo de una respuesta válida:

<img src="https://content.pstmn.io/343412d0-36d8-4ff6-a86f-38c935b91075/aW1hZ2UucG5n" width="868" height="190">

#### Código de respuesta Http 400:

Si el código de la respuesta es **400**, se trata que la solicitud enviada no cumple con la estructura requerida o una validación controlada por el PSE. El usuario debe revisar el **'MensajeError'** proporcionado por el servicio para interpretar el mensaje y corregirlo en la siguiente petición.

| **Response** |
| --- |
| {  <br>"CodigoError": "0",  <br>"MensajeError": "_Mensaje de error controlado_"  <br>} |

Ejemplo del código de respuesta 400:

<img src="https://content.pstmn.io/8b86708b-70ea-4001-839a-0105f6c992ba/aW1hZ2UucG5n" width="759" height="275">

#### Código de respuesta Http 404:

Si el código de respuesta es **404**, indica que la solicitud enviada cumple con la estructura requerida. Sin embargo, no se encontró alguna coincidencia en la búsqueda.

| **Response** |
| --- |
| {  <br>"CodigoError": "0",  <br>"MensajeError": "_Mensaje informativo de búsqueda_"  <br>} |

Ejemplo del código de respuesta 404:

<img src="https://content.pstmn.io/d6400854-fe86-42c9-8c43-159ec81ad472/aW1hZ2UucG5n" width="737" height="265">

#### Código de respuesta Http 500:

Si el código de respuesta es **500**, indica un error no controlado por el PSE, proveniente de alguna parte del servicio. En este caso, por temas de seguridad el servicio no proporcionará el mensaje detallado del error, solo el código, que será distinto de cero (0).

| **Reponse** |
| --- |
| {  <br>"CodigoError": "1511592815",  <br>"MensajeError": null  <br>} |

Ante este escenario, el usuario deberá reportarlo a los canales definidos en el acuerdo comercial, o por los mecanismos otorgados por la empresa, para que el error pueda ser aclarado o, en su defecto, resuelto.

Ejemplo del código de respuesta 500:

<img src="https://content.pstmn.io/ca6d2871-c5bd-48fa-8caa-195311db3d5f/aW1hZ2UucG5n" width="793" height="288">