## OBJETIVO

Creación de una API que gestione los productos de una tienda Online

### GET /api/products

- Recuperar todos los productos de la colección products
    - La url GET /api/products debe funcionar -> Responda con status 200
    - Debe devolver datos en formato JSON -> Responda con la cabecera Content-Type igual a application/json
    - Debe devolver un array de datos


### GET /api/products/PRODUCTID

- Recuperar un único producto a partir de si ID
    - Extraemos el id del producto de req.params
    - Para recuperar el producto podemos usar findById

### POST /api/products

- Método Product.create que recibe el body con los datos a insertar

### PUT /api/products/PRODUCTID

- Product.findByIdAndUpdate(PRODUCTID, OBJ con MODIFICACIONES)

### DELETE /api/products/PRODUCTID

### TEST
- Antes de cada prueba
    - Inserto un Documento nuevo
    - Lanzo la petición del delete sobre el documento recién insertado

- Después de todas las pruebas, borramos aquellos que tengan departamento test

- Primera prueba: status 200 y header JSON
- Segunda prueba: Recuperar el producto por ID (Product.findById) y mirar si no es NULO

#### RUTA
- Borramos a partir de Product.findByIdAndDelete

## GET /api/products/DEPARTAMENTO

- En función del departamento recibido dentro de la URL recuperamos todos aquellos productos de dicho departamento (find)

## GET /api/products/pr/PRECIO

- Recupera todos los productos cuyo precio sea mayor que el precio recibido en la URL (find)

{ price: { $gt: 10 } }

## GET /api/products/list/ASCENDENTE (asc / desc)

- Recuperamos el nombre y el precio, ordenado por precio ascendente o descendente dependiendo de lo que recuperamos en la URL

## GET /api/products/dpto/stats

## GET /api/product/pr/min/PRECIO

- Recuperamos nombre y precio de aquellos productos que estén disponibles (available) y además su precio sea mayor que el precio recuperado a través de la URL
- Ordenados por precio de manera ascendente

- $match - FILTRO { $match: { ... price: { $gt: 100 } } }
- $project
- $sort

## GET /api/products/available

- Recuperar la suma de todos los productos disponibles y no disponibles
- Contar cuántos hay de cada clase
- Contar el stock de cada clase
- Ordenar por stock de manera ascendente

- Para resolver esto hacemos un método en el modelo (availables)
    - Sin parámetros
    - Ejecuta el aggregate con las especificaciones anteriores ($group, $sort)

## POST /api/user/register

- Recibe todos los datos del usuario a través del Body
- Inserta dichos datos dentro de la BD (create)

## GET /api/users/profile

## GET /api/products/dpto/same

## GET /api/products/taxes

- Me recupere el nombre y el precio con IVA de todos los productos
    - Recuperar todos los productos
    - 

## GET /api/products/add/PRODUCTID

- Al usuario logado le agregamos el producto cuyo ID extraemos de la url
    - Recuperamos el id del producto
    - Al array de productos del usuario logado le agregamos el producto anterior

## GET /api/products/cart

- Recuperar los productos del usuario logado




