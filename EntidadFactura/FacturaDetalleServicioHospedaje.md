### Exportación de Servicios de Hospedaje

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **TipoDocumentoHuesped**  <br>`obligatorio`  <br>`number` | Código de tipo de documento de identidad del sujeto no domiciliado.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md)|  |
| **NumeroDocumentoHuesped**  <br>`obligatorio`  <br>`string` | Número de documento de identidad del sujeto no domiciliado. | Máximo de caracteres: 20. |
| **RazonSocialHuesped**  <br>`obligatorio`  <br>`string` | Apellidos y nombres o denominación o razón social del sujeto no domiciliado. | Máximo de caracteres: 200. |
| **CodigoPaisEmisionDocumentoIdentidad**  <br>`obligatorio`  <br>`string` | Código del país de emisión del pasaporte. | Solo 2 caracteres en mayúsculas que representan al país. |
| **CodigoPaisResidencia**  <br>`obligatorio`  <br>`string` | Código del país de residencia del sujeto no domiciliado. | Solo 2 caracteres en mayúsculas que representan al país. |
| **FechaIngresoPais**  <br>`obligatorio`  <br>`string` | Fecha de ingreso al país.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **FechaIngresoEstablecimiento**  <br>`obligatorio`  <br>`string` | Fecha de ingreso al Establecimiento.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **FechaSalidaEstablecimiento**  <br>`obligatorio`  <br>`string` | Fecha de salida del Establecimiento.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **FechaConsumo**  <br>`obligatorio`  <br>`string` | Fecha de consumo.  <br>**Ejemplo:**  <br>yyyy-MM-ddTHH:mm:ss | Formato ISO 8601. |
| **NumeroDiasPermanencia**  <br>`obligatorio`  <br>`number` | Número de días de permanencia. | Máximo de dígitos: 4. |