### AUTENTICACIÓN

Para que la ejecución de los servicios de generación del CPE, el XML, la firma digital y el PDF correspondiente, previamente es necesario realizar una autenticación y obtener un Token, el cual se utilizará en cada uno de los endpoints de los CPE (factura, boleta, nota de crédito, nota de débito, etc.).

El endpoint para obtener el token es el siguiente, y se necesita como dato obligatorio el número de RUC del comercio emisor:

| **Endpoint** | **Método** |
| --- | --- |
| {base_url}/api/v2/generarToken?ruc=[RUC] | GET |

Dentro de la sección “Hearders” del endpoint de generación del Token se necesita el código del comercio, el cual es único y es proporcionado por Pecano Software para trabajar con PecanoFact, tal como se muestra en el siguiente cuadro de ejemplo:

| **Heardes** |  |
| --- | --- |
| KEY_COMERCIO | 75ca3f444ea2e071577f675d04cf8dcd |

Una vez ejecutado el endpoint para la generación del Token de autenticación, la respuesta enviada por dicho endpoint es el que se muestra como en el siguiente ejemplo de prueba:

| **Response** |  |
| --- | --- |
| Token | 241475d91b99fb3a5d2aecee3bc5094c8fc025279e21cfcc9d3dcee7e391c770 |

**TIEMPO DEL TOKEN DE AUTENTICACIÓN:**  
Se debe tomar en cuenta que el tiempo permitido del token tiene una duración máxima de 1 hora.

**Código de respuesta Http 200** :  
Si el código de la respuesta es 200, significa que la solicitud enviada cumplió con los requisitos mínimos para obtener información.

<img src="https://content.pstmn.io/7e5626eb-5d67-411d-88dd-856bfc2e8b3d/aW1hZ2UucG5n" width="669" height="195">

**Código de respuesta Http 400** :  
Si el código de la respuesta es 400, se trata que la solicitud enviada no cumple con la estructura requerida o una validación controlada por el PSE. El usuario debe revisar el 'MensajeError' proporcionado por el servicio para interpretar el mensaje y corregirlo en la siguiente petición.

<img src="https://content.pstmn.io/91da8c6e-9335-4810-91a1-6311a4ffa968/aW1hZ2UucG5n" width="715" height="223">

**Código de respuesta Http 500** :  
Si el código de respuesta es 500, indica un error no controlado por el PSE, proveniente de alguna parte del servicio. En este caso, por temas de seguridad el servicio no proporcionará el mensaje detallado del error, sólo el código, que será distinto de cero (0).

<img src="https://content.pstmn.io/45c95718-356b-4529-b7fc-c8f01bbd5eb7/aW1hZ2UucG5n" width="741" height="204">