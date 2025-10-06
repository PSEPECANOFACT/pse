### DireccionEntregaBien

| **Propiedad** | **Descripción** | **Condición** |
| - | - | - |
| **DireccionCompleta**  <br>`obligatorio`  <br>`string` | Dirección completa y detallada del lugar en el que se entrega el bien.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Mínimo: 3 caracteres.  <br>Máximo: 200 caracteres.  <br>No se permiten saltos de línea ni otros caracteres similares. |
| **Urbanizacion**  <br>`opcional`  <br>`string` | Nombre de la urbanización de la dirección del lugar en el que se encuentra el bien.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Mínimo: 1 caracter.  <br>Máximo: 25 caracteres.  <br>No se permiten saltos de línea ni otros caracteres similares. |
| **CodigoUbigeo**  <br>`opcional`  <br>`string` | Código de Ubigeo de la dirección del lugar en el que se encuentra el bien. | Debe contener 6 dígitos que representen al departamento, provincia y distrito. |
| **CodigoPais**  <br>`opcional`  <br>`string` | Código de país de la dirección del lugar en el que se encuentra el bien. | Debe contener 2 caracteres que representen al país.  <br>En caso el código del país sea consignado, si el tipo de operación es "0201" o "0208", el código no debe ser "PE"; de lo contrario, si el tipo de operación es diferente de "0201" y de "0208", el código del país solo debe ser "PE". |