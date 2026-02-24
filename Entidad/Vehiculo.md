### Vehiculo

| **Propiedad** | **Descripción** | **Condición** |
| --- | --- | --- |
| **IdItem**  <br>`obligatorio`  <br>`number` | Número de orden del vehículo (numeración secuencial). | \[1\]: Principal.  <br>\[2\]: Secundario. |
| **NumeroPlaca**  <br>`obligatorio`  <br>`string` | Número de placa del vehículo. | Alfanumérico de 6 a 8 caracteres  <br>Solo letras mayúsculas y números.  <br>No espacios en blanco ni guion. |
| **NumeroCivTucChv**  <br>`condicional`  <br>`string` | Número de Constancia de Inscripción Vehicular (CIV) o Tarjeta Única de Circulación (TUC) o Certificado de Habilitación Vehicular (CHV). | Alfanumérico de 10 a 15 caracteres (solo letras mayúsculas y números). |
| **NumeroAutorizacionEspecial**  <br>`opcional`  <br>`string` | Número de autorización especial del vehículo emitido por la entidad. | Alfanumérico de 3 a 50 caracteres. |
| **EntidadEmisoraAutorizacion**  <br>`opcional`  <br>`number` | Entidad emisora de autorización especial - vehículo.  <br>[[Ver listado]](../Listado/EntidadEmisoraAutorizacionEspecial.md) | Catálogo D-37. |