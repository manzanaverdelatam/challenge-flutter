# Prueba 1

## Calcular el total de la compra.

En el archivo app_controller.dart termina de implementar el método calculateTotal de la clase CatalogCartAndCheckout. Para ello debes tener en cuenta que:

- El total se calcula de la suma del **subtotal** más el **costo de delivery**  menos el **descuento de cupón**;

- El subtotal es la suma del total de cada uno de los productos. La suma total del producto se obtiene de multiplicar el precio del producto por el número de piezas agregadas.

- Cuando el subtotal es mayor o igual a la compra mínima para envío gratis, no se cobra el envío. La compra mínima para envío gratis es 500.

- Los cupones pueden ser de dos tipos y su valor de descuento se calcula de la siguiente manera:

    - **Porcentaje** = subtotal * (valorDeCupon/100)
    - **Fijo** = valorDelCupon.

- Cuando el subtotal es menor al monto mínimo de compra del cupón, el cupón no se aplica.

- De los productos marcados como promoción se cobrará un producto menos cuando el usuario agregue más de 2 productos del mismo tipo . Es decir, si compra tres productos, pagará únicamente dos; si compra seis productos, pagará cinco.

- Algunos productos pueden tener un descuento del 10% si son comprados en paquetes. De esta manera, si tenemos:

    ``` dart
    var producto1 = {
        "id": 978,
        "price": 5000,
    };

    var producto2 = {
        "id": 324,
        "price": 1400,
    };

    var producto3 = {
        "id": 889,
        "price": 5000,
        "promotion": true,
    };

    var producto4 = {
        "id": 234,
        "price": 8900,
        "match": [889, 978]
    };
    ```
	
    Si el usuario agrega el producto1 y el producto4 a su carrito, se aplicará un descuento del 10% a cada uno de esos productos ya que el producto4 puede hacer paquete con el producto1.

- Los productos en promoción no son válidos para generar paquetes.
	
    Basándonos en el ejemplo anterior, si el usuario agrega el producto4 y el producto3, no se aplicará descuento a ninguno de los dos productos debido a que el producto3 está marcado con promoción.

- El descuento por paquete solo se puede aplicar una vez por producto.

 > Puedes usar los códigos “porcentaje” y “fijo” para obtener un cupón del tipo correspondiente en la pantalla de pago.

 > Asegúrate de mostrar el cálculo del subtotal, descuento de cupón, costo de envío y total en la pantalla de pago.

## Refactoriza

En este punto tienes la libertad de cambiar cualquier aspecto del proyecto. Las únicas dos condiciones son: que la aplicación se vea y se comporte de la misma manera, y no modificar la carpeta ./packages/api/

## Consideraciones generales.

Asegúrate de hacer commits por cada cambio relevante que hagas en el código. Para esta prueba es importante poder seguir paso a paso los cambios que realices.
