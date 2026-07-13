### ANULAR CPE

Realiza la anulación (o comunicación de baja) de cualquier CPE.

Para la ejecución del endpoint de anulación del CPE, se debe tener registrado, emitido y aprobado el CPE correspondiente por la SUNAT.

El endpoint a utilizar para la anulación de un CPE emitido es el siguiente:

| **Endpoint** | **Método** |
| --- | --- |
| {base_url}**/api/v2/cpe/anulacion** | POST |

Al igual que con la generación del CPE, en la anulación se necesita también un Token utilizable:

| **Headers** |  |
| --- | --- |
| TOKEN-PSE-PECANOFACT | 241475d91b99fb3a5d2aecee3bc5094c8fc025279e21cfcc9d3dcee7e391c770 |

Para esta acción, se debe generar un nuevo Token, en caso haya superado el tiempo de vida de 1 hora (_ver_ [001.Autenticación](./Autenticacion.md)).

En la sección del “Body” del endpoint de la anulación, se debe colocar algunos datos necesarios para realizar dicha acción, tales como:

| **Body** |
| --- |
| {  <br>"RucEmisor":"20201023221",  <br>"NumeroDocumento": "FKN1-00001010",  <br>"TipoDocumento": 10,  <br>"MotivoBaja": "Mal ingreso de información"  <br>} |

**IMPORTANTE:** Las anulaciones se enviarán a la SUNAT o al OSE dentro de los siguientes 10 minutos después de recepcionado el CPE. Este tiempo es necesario para cumplir las exigencias definidas por la SUNAT.

·

A continuación se detallan las propiedades de cada campo para el envío del JSON de la anulación del CPE:

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **RucEmisor**  <br>`obligatorio`  <br>`string` | Número de RUC del emisor. | Debe contener 11 dígitos. |
| **NumeroDocumento**  <br>`obligatorio`  <br>`string` | Serie y correlativo del comprobante.  <br>Formato: [Serie]-[Correlativo] | Máximo: 13 caracteres |
| **TipoDocumento**  <br>`obligatorio`  <br>`number` | [[Ver listado]](../Listado/TipoComprobante.md) |  |
| **MotivoBaja**  <br>`obligatorio`  <br>`number` | Descripción del motivo de la baja del comprobante. | Mínimo: 3 caracteres.  <br>Máximo: 100 caracteres. |