# CarSalesDataForReports
## Ejercicio1
En este ejercicio realice la tabla clients, colors, invoices, invoiceLines, countries, stock y dateDimension con sus respectivos datos y tipos. Además, señalé cuales eran las llaves primarias y secundarias en cada tabla, con sus relaciones:
- Clients su llave primaria es ClientID, ya que, es el identificador único de cada cliente y su llave secundaria es CountryID, debido a que, el cliente debe llevar el país desde el cual está realizando la compra. Dicho esto, ocurre una relación entre Countries con Clients.
- Invoices su llave primaria es InvoiceID, ya que, es el identificador único de cada factura y su llave secundaria es ClientID, debido a que, la factura debe llevar el identificador de cada cliente, ya que, sin un cliente no existe una factura. Dicho esto, ocurre una relación entre Clients con Invoices. También, la otra llave secundaria es InvoiceDateKey, ya que la factura debe de llevar la fecha en la que se realiza la compra. Dicho esto, ocurre una relación entre DateDimension con Invoices.
- InvoiceLines su llave primaria es InvoiceLineID, ya que, es el identificador único de cada línea de factura y sus llaves secundarias son InvoiceID y StockID, debido a que, la línea de la factura debe llevar el identificador de cada producto y el identificador de la factura. Dicho esto, ocurre una relación entre Invoices y Stock con InvoiceLines.
- Colors su llave primaria es ColorID, ya que, es el identificador único de cada color de cada carro.
- Stock su llave primaria es StockID, ya que, es el identificador único de cada producto y su llave secundaria es ColorID, debido a que, el producto debe llevar el identificador de cada color para distinguirlo. Dicho esto, ocurre una relación entre Colors con Stock.
- DateDimension su llave primaria es DateKey, ya que, es el identificador único de cada fecha.
Tiempo estimado: 30-40min


## Ejercicio 2
### Ejercicio 2.1
Realicé las clases de:
- Clients con las variables de ClientID, ClientName, address1, address2, town, county, postcode, region, outerPostode, clientType, clientSize, clientSince, isCreditWorthy, isDealer, agregando la relación por medio de una variable self.countryID, debido a que Python es un lenguaje interpretado, cuando se le asigne el valor a esa variable va a ser del objeto Country().
Con los métodos printClients(self) que imprime los datos de los clientes y printClient(self, id) imprime los datos del número de id que le pase por parámetro para ver los datos específicos de ese cliente. Finalmente, los get y set de cada atributo de la clase Client.
- Colors con las variables color, colorID, con el método de printColor(self) que imprime los datos de los colores. Finalmente, los get y set de cada atributo de la clase Color.
- Countries con las variables countryID, countryName, countryISOCode, y el método printCountries() que imprime los datos de todos los países. Finalmente, los get y set de cada atributo de la clase Country.
- Invoices con las variables de invoiceID, invoiceNumber, invoiceDate, totalDiscount, deliveryCharge, agregando la relación de composición por medio de una variable self.clientID posterior a la asignación del valor de la variable va a ser de tipo objeto Client(), usé la relación de composición ya que una factura tiene un cliente y la factura no se podría realizar sino tuviera un cliente, con el método printInvoice(self) este método imprime la factura con sus datos. Finalmente, los get y set de cada atributo de la clase Invoices.
- InvoiceLines con las variables de incoiveLineID, salePrice, lineItem, agregando la relación de composición por medio de una variable self.invoiceID = Invoices().getInvoiceID() y self.stockID = Stock().getStockID() para poder accesar al valr de invoiceID y stockID, usé la relación de composición ya que una línea de factura tiene un id de la factura y un id del producto y la línea de la factura no se podría realizar sino tuviera esos datos y el método printInvoiceLine(self) que imprime los datos de las líneas de las facturas. Finalmente, los get y set de cada atributo de la clase InvoicesLines.
- DateDimension con las variables de DateKey, Year, MonthNum, MonthFull, MonthAbbr, QuarterNum, QuarterFull, QuarterAbbr, YearAndQuarterNum, QuarterAbbrAndYear, MonthAbbrAndYear,
MonthAndYear, MonthName, MonthNameAbbr, QuarterAndYear, QuarterAndYearAbbr2, YearAndMonthNum y el método printDate(self) que imprime todas las fechas. Finalmente, los get y set de cada atributo de la clase DateDimension.
- Stock con la variable listaAutos que recibe un Vehicle() con los datos del vehículo, con los métodos printStock(self), addStock(self) que añade nuevos vehículos a la lista y removeStock(self, id) que elimina el producto que yo le mandé por parámetros.
- Utilicé clases Contenedoras de Invoices, Client haciendo referencia al principio de responsabilidad única, en la cual agregué los métodos de add(), remove (id) para eliminar la factura por medio del id y update (id) añadiendo funcionalidad con listas.

###  Ejercicio 2.2
Realicé la clase padre ContenedoraTipoVehiculo, en la que añadí la variable de listaTipoVehiculo que va a ser una lista de strings, la cual permite agregar nuevos tipos de vehículos, además, agregué los métodos de add, remove y update.
Tiempo estimado: 2h


## Ejercicio 3:
Intenté investigar en pandas pero realmente los resultados obtenidos no eran los deseados y por lo que decidí hacer las consultas en Oracle sql developer.
### Ejercicio 3.1:
Para poder hacer este ejercicio seleccione primero la marca, luego utilicé el count para que me hiciera la cuenta del total de las casillas de las marcas de los productos, luego hice el join para relacionarla con invoiceLines ya que, la línea de la factura debe llevar el identificador de cada producto, seguidamente realicé otro join para relacionarla con Invoices ya que, cada factura debe llevar la línea de factura. Por consiguiente, utilicé el where para poder decir de donde a donde quería buscar los registros de las marcas, con lo cual el regexp_like me permitió hacer la búsqueda del año que empezará por el 2015 y los meses del primer y tercer trimestre, agrupándolos por la marca del vehículo.
### Ejercicio 3.2: 
Para poder hacer este ejercicio seleccione primero el color, luego utilicé el count para que me hiciera la cuenta del total de las casillas de los colores de los productos, luego hice el join para relacionarla con el StockID ya que, cada producto lleva un color, seguidamente realicé otro join para relacionarla con InvoiceLines ya que, cada línea de factura debe llevar el identificador de cada producto, por último, realicé otro join para relacionar con Invoices ya que, cada factura debe de llevar la línea de factura. Por consiguiente, utilicé el where para poder decir de donde a donde quería buscar los registros de las marcas, con lo cual el not like me permitió hacer la búsqueda para poder decirle que buscará en todos los años menos en los que empezarán por el 2015, ya que según los registros no hay del 2015, agrupándolos por el color del vehículo.
Tiempo estimado: 1h
