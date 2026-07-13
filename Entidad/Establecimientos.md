### Establecimientos

| Propiedad                                                    | Descripción                                                                 | **Condición**                 |
| ------------------------------------------------------------ | --------------------------------------------------------------------------- | ----------------------------- |
| **TipoEstablecimiento**  <br>`obligatorio`  <br>`number`  | Tipo de establecimiento de la dirección  <br>[[Ver listado]](../Listado/TipoEstablecimiento.md) | Usar los valores del listado. |
| **Direccion**  <br>`obligatorio`  <br>`string` |Dirección del establecimiento                 | Máximo 200 caracteres.                              |
| **EsEstablecimientoEmision**  <br>`bool` |Indicador del establecimiento para indicar que es un establecimiento de emision del comprobante. | Solo puede haber un indicador en true por comprobante. |
