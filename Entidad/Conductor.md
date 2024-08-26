### Conductor

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de orden del conductor (numeración secuencial). | \[1\]: Principal.  <br>\[2\]: Secundario. |
| **TipoDocumentoIdentidad**  <br>`obligatorio`  <br>`number` | Tipo de documento de identidad del conductor.  <br>[[Ver listado]](../Listado/TipoDocumentoIdentidad.md) | Catálogo 6. |
| **ValorDocumentoIdentidad**  <br>`obligatorio`  <br>`string` | Número de documento de identidad del conductor. | Alfanumérico de hasta 15 caracteres. |
| **NombresConductor**  <br>`obligatorio`  <br>`string` | Nombres del conductor. | Alfanumérico de hasta 150 caracteres. |
| **ApellidosConductor**  <br>`obligatorio`  <br>`string` | Apellidos del conductor. | Alfanumérico de hasta 150 caracteres. |
| **NumeroLicenciaConducir**  <br>`obligatorio`  <br>`string` | Número de licencia de conducir. | Alfanumérico de 9 a 10 caracteres.  <br>Solo letras mayúsculas y números. |