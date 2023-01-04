# BIENVENIDOS AL CHALLANGE

## A CONTINUACIÓN SE DOCUMENTARA EL PROYECTO. COMO SE DEBE DE EJECUTAR EL SERVIDOR Y EL CLIENTE. SE DESCRIBEN LOS TEST, LAS FUNCIONES Y COMO USAR LO BOTONES

## PRIMERO EJECUTAR 

- npm install


## EJECUTAR EL SERVIDOR

PARA DESARROLLAR EL SERVIDOR UTILICE LA VERSIÓN  NodeJS 14.21.2

PARA EJECUTARLO DE DEBE DE INGRESAR A Toolbox\server. UNA VEZ DENTRO EJECUTAR EL SIGUIENTE COMANDO DENTRO DE UNA TERMINAL 

- npm start

PARA VER LA TODA LA DATA INGRESAR A 

- http://localhost:5000/files/data

PARA VER LA DATA DE UN ARCHIVO INGRESAR A 

- http://localhost:5000/files/data?filename="Nombre del archivo"

EJEMPLO:

- http://localhost:5000/files/data?filename=test6.csv

PARA VER LA LISTA DE ARCHIVOS DISPONIBLES INGRESAR A 

- http://localhost:5000/files/list

* EN LA CLASE index.js DEL SERVIDOR ES DONDE SE CREA AL MISMO, SETEANDO LAS RUTAS Y LA DATA A RETORNAR PARA CADA UNA DE ELLAS.

## EJECUTAR EL CLIENTE

PARA DESARROLLAR EL SERVIDOR UTILICE LA VERSIÓN  NodeJS 16.1.0

PARA EJECUTAR EL CLIENTE INGRESE A Toolbox\client. UNA VEZ DENTRO EJECUTAR EL SIGUIENTE COMANDO DENTRO DE UNA TERMINAL 

- npm start

LUEGO INGRESAR A LA SIGUIENTE URL

- http://localhost:3000/

## USO DE LOS BOTONES

### IMPORTANTE

LUEGO DE HACER CLIC EN UNO DE ELLOS, POR FAVOR ACTUALIZAR LA PÁGINA.

## EJECUTAR LOS TEST

### TEST DEL SERVIDOR

PARA EJECUTARLO LOS TEST DEL SERVIDOR SE DEBE DE INGRESAR A Toolbox\server Y EJECUTAR EL COMANDO 

- npm run test  

EN CASO DE QUE EL SERVIDOR ESTE LEVANTADO, POR FAVOR BAJAR EL MISMO. PARA ESTO EN LA TERMINAL DE SEDE DE OPRIMIR LAS TECLAS Ctrl C. ESTO SE DEBE A QUE LOS TEST DEL SERVIDOR VUELVEN A LEVANTAR. 

PARA REALIZAR LOS TEST SE USÓ Mocha + Chai

* EL TEST csvTojson.spec.js SE ENCARGA DE TESTEAR QUE SE TRANSFORME UNA ARCHIVO CSV A UN ARCHIVO JSON

* EL TEST externalApi.spec.js SE ENCARGA DE TESTEAR QUE CUANDO SE LLAME A LA API EXTERNA DEVUELVA LA DATA CORRESPONDIENTE.

* EL TEST externalApiGetAllfiles.spec.js SE ENCARGA DE TESTEAR QUE ESTÉN PRESENTES LAS KEY YA QUE ES UNA MANERA DE ASEGURARSE QUE SE ESTÁ OBTENIENDO LA DATA. NO EVALÚO LOS VALORES DE LAS KEY YA QUE ESTOS EN LA API EXTERNA PUEDEN VARIAR.

* EL TEST externalApiGetDataFile.spec.js SE ENCARGA DE TESTEAR QUE ESTÉN PRESENTES LAS KEY EN EL ARCHIVO CORRESPONDIENTE. NO EVALÚO LOS VALORES DE LAS KEY YA QUE ESTOS EN LA API EXTERNA PUEDEN VARIAR.

* EL TEST index.spec.js SE ENCARGA DE TESTEAR QUE EL SERVIDOR SE LEVANTE Y LOS ENDPOINTS

### TEST DEL CLIENTE

PARA EJECUTARLO LOS TEST DEL CLIENTE SE DEBE DE INGRESAR A Toolbox\client Y EJECUTAR EL COMANDO 

- npm run test

ES IMPORTANTE QUE EL SERVIDOR ESTÉ LEVANTADO PARA QUE LOS TEST DEL CLIENTE PASEN CORRECTAMENTE.

PARA REALIZAR LOS TEST SE USÓ Jest

* EL TEST buttons.spec.js SE ENCARGA DE TESTEAR QUE EL COMPONENTE buttons ES RENDERIZADO Y QUE LOS BOTONES ESTÉN PRESENTES.

* EL TEST header.spec.js SE ENCARGA DE TESTEAR QUE EL COMPONENTE header ES RENDERIZADO Y QUE EL TÍTULO ESTE PRESENTE.

* EL TEST table.spec.js SE ENCARGA DE TESTEAR QUE EL COMPONENTE table ES RENDERIZADO, QUE ENCABEZADO DE LA TABLA TENGA SUS VALORES CORRRESPONDIENTES Y QUE EL NOMBRE DE UNO DE LOS ARCHIVOS ESTE PRESENTE.

## FUNCIONES

### externalApiFunctions

* externalApi

LA FUNCIÓN externalApi REALIZA UN FETCH A externalApi https://echo-serv.tbxnet.com/v1/secret/files Y DEVUELVE UN STRING QUE CONTIENE TODOS LOS NOMBRES DE LOS ARCHIVOS

* externalApiGetAllfiles

LA FUNCIÓN externalApiGetAllDatafiles OBTIENE LA DATA DE CADA UNO DE LOS ARCHIVOS DISPONIBLES Y LOS ALMACENA EN UN ARRAY, RETORNANDO UN OBJETO CON TODA LA DATA DE TODOS LOS ARCHIVOS.

* externalApiGetDataFile

LA FUNCIÓN externalApiGetDataFile RECIBE POR PARÁMETRO fileName, QUE ES EL NOMBRE DE UN ARCHIVO Y OBTIENE LA DATA DEL MISMO, ALMACENÁNDOLA EN UN ARRAY, PARA LUEGO RETORNAR UN OBJETO CON TODA LA DATA DEL ARCHIVO.

### utils

* csvTojson 

LA FUNCIÓN csvTojson RECIBE POR PARÁMETRO UN ARCHIVO CSV Y LO TRANSFORMA EN UN OBJETO JSON.