### Detracciones - Servicio de transporte de carga - detalle de el(los) vehículo(s)

| **Propiedad** | **Descripción** | **Condición** |
| - | - | - |
| **IdItemVehiculo**  <br>`obligatorio`  <br>`number` | Número de ítem del vehículo del tramo del servicio de transporte de carga de la detracción del detalle del comprobante.  | Mínimo: 1.  <br>Máximo: 99.  |
| **ConfiguracionVehicularVehiculo**  <br>`opcional`  <br>`string` | Configuración vehicular del vehículo. | Alfanumérico de 1 a 15, incluido espacios. |
| **CargaUtilEnToneladasMetricasVehiculo**  <br>`opcional`  <br>`number` | Carga útil en toneladas métricas del vehículo. | Positivo mayor que cero. |
| **CargaEfectivaEnToneladasMetricasVehiculo**  <br>`opcional`  <br>`number` | Carga efectiva en toneladas métricas del vehículo. | Positivo mayor que cero. |
| **ValorReferencialPorToneladaMetrica**  <br>`opcional`  <br>`number` | Valor referencial por tonelada métrica. | Positivo mayor que cero. |
| **IndicadorAplicacionFactorRetornoVacio**  <br>`opcional`  <br>`number` | Indicador de aplicación de factor de retorno al vacío. | Los valores pueden ser: true o false. |