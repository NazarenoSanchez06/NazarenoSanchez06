#   Simulación check-in de aerolínea

## Tabla de contenidos

1. [Descripción](#descripción)
2. [Instalación](#instalación)
3. [Tecnologías utilizadas](#Tecnologías-utilizados)
4. [Demo](#demo)
5. [Autor](#Autor)

## Descripción
En el ejercicio se necesitas desarrollar una API REST con un único endpoint que permita consultar por el ID del vuelo y retorne la simulación de un check-in automático de los pasajeros de la aerolínea Andes Airlines. Además, se cuenta con una base de datos en MySQL de solo lectura que se utilizará para la simulación. Tienes total libertad para elegir el lenguaje de programación y el framework que desees utilizar.

ERD
![erd](https://user-images.githubusercontent.com/61089189/228735639-08f7e264-8b2b-4c24-962d-c719dc37626f.png)

1. Detalles del ejercicio:
2. Una compra puede tener múltiples tarjetas de embarque asociadas.
3. Las tarjetas de embarque pueden no tener un asiento asociado inicialmente, pero siempre tendrán un tipo de asiento.
4. Al retornar la simulación del check-in, se debe asignar un asiento a cada tarjeta de embarque.
5. Los pasajeros menores de edad deben estar sentados junto a al menos uno de sus acompañantes mayores de edad. Esto se puede lograr agrupando por el ID de la compra.
6. En la medida de lo posible, si una compra tiene varias tarjetas de embarque, se debe intentar asignar asientos contiguos o cercanos (ya sea en la fila o en la columna).
7. Si una tarjeta de embarque pertenece a la clase "económica", no se puede asignar un asiento de otra clase.

8. El servicio debe tener la siguiente estructura:
```
Método: GET
Ruta: /flights/:id/passengers
Respuesta exitosa:
{
 "code": 200,
 "data": {
    "flightId": 1,
    "takeoffDateTime": 1688207580,
    "takeoffAirport": "Aeropuerto Internacional Arturo Merino Benitez, Chile",
    "landingDateTime": 1688221980,
    "landingAirport": "Aeropuerto Internacional Jorge Cháve, Perú",
    "airplaneId": 1,
    "passengers": [
       {
            "passengerId": 90,
            "dni": 983834822,
            "name": "Marisol",
            "age": 44,
            "country": "México",
            "boardingPassId": 24,
            "purchaseId": 47,
            "seatTypeId": 1,
            "seatId": 1
        },
        {...}
    ]
 }
}
```

Vuelo no encontrado:

```
{
"code": 404,
"data": {}
}
```

En caso de error:

```
{
"code": 400,
"errors": "could not connect to db"
}

```

## Instalación


1. Clonar el proyecto

```bash
$ git clone https://github.com/NazarenoSanchez06/Desafio-Bsale.git
```

2. Acceder al directorio del proyecto

```bash
$ cd "carpeta donde se clonó"
```

3. instalar las dependencias

```bash
$ npm install
```

4. Ejecución

```bash
$ npm run dev
```

5. Utilizar la siguiente ruta y hacer la prueba en alguna herremienta de probar APIs(Posmant/- Extención de Visual Studio Code Thunder Client)

```sh
http://localhost:3000/flights/id/passengers
```

## Tecnologías utilizadas

* **TypeScript** (v. 4.9.4) [Source](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html)
* **Express** (v. 4.18.2)  [Source](https://www.npmjs.com/package/express)
* **Prisma** (v. 4.9.0) [Source](https://www.prisma.io/docs)
* **nodemon** (v. 2.0.20) [Source](https://www.npmjs.com/package/nodemon)
* **cors** (v. 2.8.5) [Source](https://www.npmjs.com/package/cors)
* **dotenv** (v. 16.0.3) [Source](https://www.npmjs.com/package/dotenv)
* **concurently**  (v. 7.6.0) [Source](https://www.npmjs.com/package/concurrently)
* **ts-node**  (v. 10.9.1) [Source](https://www.npmjs.com/package/ts-node)
* **tslib**  (v. 2.4.1) [Source](https://www.npmjs.com/package/tslib)
* **ts-retry-promise** (v. 0.7.0) [Source](https://www.npmjs.com/package/ts-retry-promise)



## Demo
Para el despliegue del proyecto se utilizó Vercel.

[![Deploy with Vercel](https://vercel.com/button)](https://simulacion-check-in-aerolinea.vercel.app)


## Autor
- [Gefferson Casasola](https://github.com/Geffrerson7)
