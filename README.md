# CarSalesDataForReports
## Ejercicio1
En este ejercicio realice la tabla clients, colors, invoices, invoiceLines, countries, stock y dateDimension con sus respectivos datos y tipos. Además, señalé cuales eran las llaves primarias y secundarias en cada tabla, con sus relaciones:
### Clients su llave primaria es ClientID, ya que, es el identificador único de cada cliente y su llave secundaria es CountryID, debido a que, el cliente debe llevar el país desde el cual está realizando la compra. Dicho esto, ocurre una relación entre Countries con Clients.
### Invoices su llave primaria es InvoiceID, ya que, es el identificador único de cada factura y su llave secundaria es ClientID, debido a que, la factura debe llevar el identificador de cada cliente, ya que, sin un cliente no existe una factura. Dicho esto, ocurre una relación entre Clients con Invoices. También, la otra llave secundaria es InvoiceDateKey, ya que la factura debe de llevar la fecha en la que se realiza la compra. Dicho esto, ocurre una relación entre DateDimension con Invoices.
### InvoiceLines su llave primaria es InvoiceLineID, ya que, es el identificador único de cada línea de factura y sus llaves secundarias son InvoiceID y StockID, debido a que, la línea de la factura debe llevar el identificador de cada producto y el identificador de la factura. Dicho esto, ocurre una relación entre Invoices y Stock con InvoiceLines.
### Colors su llave primaria es ColorID, ya que, es el identificador único de cada color de cada carro.
### Stock su llave primaria es StockID, ya que, es el identificador único de cada producto y su llave secundaria es ColorID, debido a que, el producto debe llevar el identificador de cada color para distinguirlo. Dicho esto, ocurre una relación entre Colors con Stock.
### DateDimension su llave primaria es DateKey, ya que, es el identificador único de cada fecha.
Tiempo estimado: 30-40min
