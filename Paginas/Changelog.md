# Changelog | API PSE ONLINE
Todos los cambios notables de este proyecto se documentarán en este archivo.

## [1.0.0] - 2024-10-xx
### Added
- Generar token con tiempo de expiración para autenticar y autorizar las solicitudes de los comercios.
- Firmar el documento electrónico según la configuración del comercio. **(SEE del contribuyente o PSE)**
- Generar documento electrónico de factura. **(XML)**
- Generar documento electrónico de boleta. **(XML)**
- Generar documento electrónico de nota de crédito. **(XML)**
- Generar documento electrónico de nota de débito. **(XML)**
- Generar documento electrónico de guía de remisión remitente. **(XML)**
- Generar documento electrónico de guía de remisión transportista. **(XML)**
- Anular documentos electrónicos de facturas, boletas de venta, notas de crédito y notas de débito.
- Consultar por documento si el comprobante ha sido enviado al PSE Cloud.
- Consultar por fecha si los comprobantes han sido enviados al PSE Cloud.
- Consultar por rango de fecha si los comprobantes han sido enviados al PSE Cloud.

----

## [2.0.0] - 2024-02-xx
### Added
- Nuevo campo para el IGV de las operaciones gravadas gratuitas (_IgvGratuito_), y dejar el campo actual para las operaciones gravadas onerosas (_Igv_) para el documento electrónico de factura. **(XML)**
- Nuevo campo que puede almacenar, opcionalmente, una unidad de medida personalizada (_UnidadMedidaAlias_) para la representación impresa del documento electrónico de factura. **(PDF)**
- Nuevo campo que puede almacenar, opcionalmente, una unidad de medida personalizada (_UnidadMedidaAlias_) para la representación impresa del documento electrónico de boleta. **(PDF)**
- Nuevo campo que puede almacenar, opcionalmente, una unidad de medida personalizada (_UnidadMedidaAlias_) para la representación impresa del documento electrónico de nota de crédito. **(PDF)**
- Nuevo campo que puede almacenar, opcionalmente, una unidad de medida personalizada (_UnidadMedidaAlias_) para la representación impresa del documento electrónico de nota de débito. **(PDF)**
- Generar documento electrónico de comprobante de retención. **(XML)**
- Generar documento electrónico de comprobante de percepción. **(XML)**
- Agregar nuevos indicadores al documento electrónico de la guía de remisión remitente. **(XML)**
- Agregar nueva sección "Comprador" al documento electrónico de la guía de remisión remitente. **(XML)**
- Agregar nuevos indicadores al documento electrónico de la guía de remisión transportista. **(XML)**
- Consultar por documento si el comprobante ha sido enviado al PSE Cloud y obtener el archivo correspondiente.
- Sanitización de campos de cadena en los documentos electrónicos de facturas, boletas de venta, notas de crédito, notas de débito, comprobantes de retención, comprobantes de percepción, guías de remisión remitente y guías de remisión transportista. **(XML)**

### Modified
- Anular documentos electrónicos de comprobantes para incluir los comprobantes de retenciones y de percepciones.
- Cambio en las longitudes de los campos de tipo 'cadena' para que sus valores sean iguales a los establecidos por la SUNAT.