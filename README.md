#   Simulación check-in de aerolínea

## Tabla de contenidos

1. [Descripción](#Dx|escripción)
2. [Instalación](#Instalación)
3. [Tecnologías utilizadas](#Tecnologías-utilizados)
4. [Autor](#Autor)

## Descripción
En el ejercicio se necesitas desarrollar una API REST con un único endpoint que permita consultar por el ID del vuelo y retorne la simulación de un check-in automático de los pasajeros de la aerolínea Andes Airlines. Además, se cuenta con una base de datos en MySQL de solo lectura que se utilizará para la simulación. con  total libertad de elegir el lenguaje de programación y el framework que desees utilizar.
* ERD


![erd](https://user-images.githubusercontent.com/61089189/228735639-08f7e264-8b2b-4c24-962d-c719dc37626f.png)


   Detalles del ejercicio:
1. Una compra puede tener múltiples tarjetas de embarque asociadas.
2. Las tarjetas de embarque pueden no tener un asiento asociado inicialmente, pero siempre tendrán un tipo de asiento.
3. Al retornar la simulación del check-in, se debe asignar un asiento a cada tarjeta de embarque.
4. Los pasajeros menores de edad deben estar sentados junto a al menos uno de sus acompañantes mayores de edad. Esto se puede lograr agrupando por el ID de la compra.
5. En la medida de lo posible, si una compra tiene varias tarjetas de embarque, se debe intentar asignar asientos contiguos o cercanos (ya sea en la fila o en la columna).
6. Si una tarjeta de embarque pertenece a la clase "económica", no se puede asignar un asiento de otra clase.

7. El servicio debe tener la siguiente estructura:
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

3. Instalar las dependencias

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

* **JavaScript**<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="25" height="25"/>
* **MySQL** <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original.svg" alt="MySQL" width="25" height="25"/> 
* **mysql2** <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original.svg" alt="MySQL" width="25" height="25"/> 
* **Express** <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original.svg" alt="Express" width="25" height="25"/> 
* **Nodejs** <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original.svg" alt="Node.js" width="25" height="25"/>
* **dotenv**


## Autor
- Nazareno Salvador Sanchez Pacherres
