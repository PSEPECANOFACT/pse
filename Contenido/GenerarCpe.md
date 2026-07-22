### GENERAR CPE

Para conocer los detalles de los campos del JSON, descripción y condiciones de cada tipo de comprobante, haga clic en sus respectivos enlaces:

| Tipo de Comprobante | Enlace |
| --- | --- |
| Factura (01) | [EntidadFactura/Factura.md](../EntidadFactura/Factura.md) |
| Boleta de Venta (03) | [EntidadBoleta/Boleta.md](../EntidadBoleta/Boleta.md) |
| Nota de Crédito (07) | [EntidadNotaCredito/NotaCredito.md](../EntidadNotaCredito/NotaCredito.md) |
| Nota de Débito (08) | [EntidadNotaDebito/NotaDebito.md](../EntidadNotaDebito/NotaDebito.md) |
| Comprobante de Retención (20) | [EntidadRetencion/Retencion.md](../EntidadRetencion/Retencion.md) |
| Comprobante de Percepción (40) | [EntidadPercepcion/Percepcion.md](../EntidadPercepcion/Percepcion.md) |
| Guía de Remisión Remitente (09) | [EntidadGuiaRemitente/GuiaRemitente.md](../EntidadGuiaRemitente/GuiaRemitente.md) |
| Guía de Remisión Transportista (31) | [EntidadGuiaTransportista/GuiaTransportista.md](../EntidadGuiaTransportista/GuiaTransportista.md) |

.
Para la generación del CPE se debe ejecutar el siguiente endpoint:

| **Tipo de Comprobante** | **Endpoint** | **Método** |
| --- | --- | --- |
| Factura | {base_url}**/api/v2/cpe/factura** | POST |
| Boleta de Venta | {base_url}**/api/v2/cpe/boleta** | POST |
| Nota de Crédito | {base_url}**/api/v2/cpe/notacredito** | POST |
| Nota de Débito | {base_url}**/api/v2/cpe/notadebito** | POST |
| Comprobante de Retención | {base_url}**/api/v2/cpe/retencion** | POST |
| Comprobante de Percepción | {base_url}**/api/v2/cpe/percepcion** | POST |
| Guía de Remisión Remitente | {base_url}**/api/v2/cpe/guiaremitente** | POST |
| Guía de Remisión Transportista | {base_url}**/api/v2/cpe/guiatransportista** | POST |
| Resumen Diario | {base_url}**/api/v2/cpe/online/resumendiario** | POST |
| Comunicación de Baja | {base_url}**/api/v2/cpe/online/comunicacionbaja** | POST |
| Resumen de Reversión | {base_url}**/api/v2/cpe/online/resumenreversion** | POST |

Dentro de la sección “Hearders” del endpoint, se debe configurar el siguiente valor con el valor del Token de autorización obtenido anteriormente:

| **Headers** |  |
| --- | --- |
| TOKEN-PSE-PECANOFACT | 241475d91b99fb3a5d2aecee3bc5094c8fc025279e21cfcc9d3dcee7e391c770 |

En la sección “Body” se debe ingresar toda la información necesaria para generar el CPE. Esta información debe ser enviado en formato JSON con los datos especificados por Pecano para el endpoint:

| **Body** |
| --- |
| _Representación en formato JSON de los datos requeridos de la factura para la generación del CPE._ |

·

**Códigos de respuestas (StatusCode) obtenidos:**

Como respuestas a la ejecución del endpoint correspondiente al CPE, las respuestas pueden variar según el resultado obtenido.

Si el código de la respuesta es **200**, entonces la respuesta obtenida es válida ("OK") y devuelve el XML (en formato 64) y el DisgestValue:

| **Response** |
| --- |
| _**XML**_ en formato 64 obtenido después de ejecutar el endpoint del CPE.  <br>_**DigestValue**_ obtenido después de ejecutar el endpoint del CPE. |

Si el código de la respuesta es **400**, se trata de un error controlado por el PSE y que el usuario debe tomar en cuenta el 'mensaje de error'. El código de error es cero (0):

| **Response** |
| --- |
| {  <br>"CodigoError": "0",  <br>"MensajeError": "_Mensaje de error controlado_"  <br>} |

Si el código de la respuesta es **500**, se trata de un error no controlado por el PSE y es un error del propio servidor externo el cual no expone el mensaje de error, sino el código. En este caso, el código de error es diferente que cero (0):

| **Reponse** |
| --- |
| {  <br>"CodigoError": "1511592815",  <br>"MensajeError": null  <br>} |

En el ejemplo anterior, el error depende del servidor externo después de haber pasado las validaciones correspondientes por parte del PSE, pero no se muestra el mensaje devuelto por temas de seguridad.

Ante este escenario, el usuario deberá reportarlo a los canales definidos en el acuerdo comercial, o por los mecanismos otorgados por la empresa, para que el error pueda ser aclarado o, en su defecto, resuelto.