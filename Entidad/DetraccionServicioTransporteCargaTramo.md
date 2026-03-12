### Detracciones - Servicio de transporte de carga - detalle de tramos

| **Propiedad** | **Descripción** | **Condición** |
| - | - | - |
| **IdItemTramo**  <br>`obligatorio`  <br>`number` | Número de ítem del tramo del servicio de transporte de carga de la detracción del detalle del comprobante. | Mínimo: 1.  <br>Máximo: 99.   |
| **IdentificadorTramo**  <br>`obligatorio`  <br>`string` | Identificador del tramo. | Sin validación.  <br>Ejemplo: del "1" al "99" ("01", 1", etc.) |
| **DescripcionTramo**  <br>`opcional`  <br>`string` | Descripción del tramo. | Alfanumérico de 3 a 100, incluido espacios. |
| **UbigeoPuntoOrigenViaje**  <br>`opcional`  <br>`string` | Punto de origen del viaje. | 6 dígitos.  <br>Catálogo 13. |
| **UbigeoPuntoDestinoViaje**  <br>`opcional`  <br>`string` | Punto de destino del viaje. | 6 dígitos.  <br>Catálogo 13. |
| **ValorPreliminarReferencialSobreCargaEfectiva**  <br>`opcional`  <br>`number` | Valor preliminar referencial sobre la carga efectiva (Por el tramo virtual recorrido). | Positivo mayor que cero. |
| **ValorPreliminarReferencialPorCargaUtilNominal**  <br>`opcional`  <br>`number` | Valor preliminar referencial por carga útil nominal (Tratándose de más de 1 vehículo). | Positivo mayor que cero. |
| **DetalleVehiculo**  <br>`opcional`  <br>`array` | Información adicional - detracciones - servicio de transporte de carga - detalle de el(los) vehículo(s).  <br>[[Ver entidad]](../Entidad/DetraccionServicioTransporteCargaVehiculo.md) | Mínimo: 0 o ninguno.  <br>Máximo: 99. |