# Hello Blockchain project

Pasos para levantar una blockchain local con Ganache y truffle.

Previamente debemos crear una carpeta donde alojaremos nuestro proyecto.

1- En una terminal apuntando a nuestra carpeta de proyecto,
    ejecutar `truffle init` para crear un proyecto de truffle

2- Sobre el archivo `truffle-config.js` descomentar las lineas del entorno de development
    (Lineas 44 a 48). Tener en cuenta que el host y el puerto sean los mismo que utiliza Ganache

3- Crear archivos de contratos en la carpeta de contracts

4- Crear archivo de migration en la carpeta de migrations

5- Abrir 2 terminales apuntando a la carpeta del proyecto.
    a) 1era Terminal para Ganache
    b) 2da Terminal para Truffle

6- Ejecutar `nvm use 14` para utilizar la version 14 de npm en ambas terminales

7- Ejecutar en la 1er terminal `ganache-cli` para inicializar la blockchain local

8- Ejecutar en la 2da terminal `truffle console --network development`

9- Para comprobar que el entorno quedo listo para usar, debemos ver las siguientes lineas
    de codigo en la terminal nde Ganache:

  `net_version`
  `eth_accounts`
  `eth_accounts`
  `eth_blockNumber`
  `net_version`
  `eth_accounts`
  `eth_accounts`

  Ademas debemos ver en la terminal de Truffle el indicador `truffle<development>`

10- Podemos verificar la conexion entre Truffle y Ganache con el comando `web3.eth.getBlock(0)`

11- Ejecutar `compile` en la terminal Truffle

12- Ejecutar `migrate` en la terminal Truffle (Podemos ver el Summary del deploy del contrato)

13- Para interactuar con el contrato debemos crear una instancia con el comando:

  `const intance = await {Nombre_del_contrato}.deployed()`

  _Ejemplo_: `const intance = await HelloBlockchain.deployed()`

14- Por ultimo, tenemos que hacer llamada a la funciones con el comando:

  `intance.{Nombre_de_la_funcion}.call()`

  _Ejemplo_: `intance.sayHi.call()`

  En la terminal Truffle vemos la respuesta de la funcion:

  `Hello blockchain!`

  En la terminal Ganache vemos la llamada a la funcion `eth_call`

