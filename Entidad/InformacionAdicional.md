### InformacionAdicional

| **Propiedad**                                        | **Descripción**                                                       | **Condición**          |
| ---------------------------------------------------- | ----------------------------------------------------------------------| ---------------------- |
| **IdItem**  <br>`obligatorio`  <br>`number`          | Número o identificador de la información adicional del comprobante.   | Mínimo: 1.  <br>Máximo: 100. |
| **EtiquetaCampo**  <br>`obligatorio`  <br>`string`   | Etiqueta del campo que aparecerá en la representación impresa.        | Máximo 100 caracteres. |
| **Valor**  <br>`obligatorio`  <br>`string`           | Valor de la información adicional.  <br>[_[Campo sanitizado]_](../Paginas/CampoSanitizado.md) | Máximo 200 caracteres. |
| **TipoVisibilidad**  <br>`obligatorio`  <br>`number` | Tipo de visibilidad de la información adicional.  <br>[[Ver listado]](../Listado/TipoVisibilidadInfoAdicional.md) |  |