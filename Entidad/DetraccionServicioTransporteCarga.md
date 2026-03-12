### Detracciones - Servicio de transporte de carga

| **Propiedad** | **Descripción** | **Condición** |
| - | - | - |
| **UbigeoPuntoOrigen**  <br>`obligatorio`  <br>`string` | Código de Ubigeo del Punto de origen. | 6 dígitos.  <br>Catálogo 13. |
| **DireccionDetalladaPuntoOrigen**  <br>`obligatorio`  <br>`string` | Dirección detallada del Punto de origen. | Alfanumérico de 3 a 200, incluido espacios. |
| **UbigeoPuntoDestino**  <br>`obligatorio`  <br>`string` | Código de Ubigeo del Punto de origen. | 6 dígitos.  <br>Catálogo 13. |
| **DireccionDetalladaPuntoDestino**  <br>`obligatorio`  <br>`string` | Dirección detallada del Punto de destino. | Alfanumérico de 3 a 200, incluido espacios. |
| **DetalleViaje**  <br>`obligatorio`  <br>`string` | Detalle del viaje. | Alfanumérico de 3 a 500, incluido espacios. |
| **ValorReferencialServicioTransporte**  <br>`obligatorio`  <br>`number` | Valor referencial del servicio de transporte. | Positivo mayor que cero. |
| **ValorReferencialSobreCargaEfectiva**  <br>`obligatorio`  <br>`number` | Valor referencial sobre la carga efectiva. | Positivo mayor que cero. |
| **ValorReferencialSobreCargaUtilNominal**  <br>`obligatorio`  <br>`number` | Valor referencial sobre la carga útil nominal. | Positivo mayor que cero. |
| **DetalleTramo**  <br>`obligatorio`  <br>`array` | Información adicional - detracciones - servicio de transporte de carga - detalle de tramos.  <br>[[Ver entidad]](../Entidad/DetraccionServicioTransporteCargaTramo.md) | Mínimo: 0 o ninguno.  <br>Máximo: 99. |