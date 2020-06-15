<img src="https://www.ucm.es/data/cont/docs/3-2016-07-21-EscudoUCMTransparenteBig.png" height="70"/>              <img src="https://upload.wikimedia.org/wikipedia/commons/c/cf/Logo_Bicimad_-_EMT.png" alt="drawing" height="50"/>

## Uso nocturno de BiciMAD

*BiciMAD es un servicio de préstamo de bicicletas ofrecido por la Comunidad de Madrid. A diferencia que el Metro de Madrid, los usuarios sí pueden hacer uso de este servicio de madrugada. Esta característica nos hizo cuestioinarnos qué uso real tiene biciMAD en horarios nocturnos.*

###### A continuación se podrá encontrar una pequeña guía sobre las diferentes secciones del Notebook.

### 1. Setup
Se descargarán todos los módulos necesarios de python que se necesitarán en las diferentes secciones.
> **Necesario ejecutar**.

### 2. Descargamos los datasets de biciMAD
Se descargarán de forma automática todos los [datasets necesarios](https://opendata.emtmadrid.es/Datos-estaticos/Datos-generales-(1)) *(Enero2019-Junio2019)*  tanto los *datos de uso* como las *situaciones de estaciones*. Estos a su vez se organizarán en directorios para su fácil acceso. Los *datasets de uso* se almacenaran en la ruta `datasets/usages/` y de forma similar los *datasets de situación* en la ruta `datasets/usages/`. 
> ***Nota:** si ya tiene los datasets indicados descargados, puede disponerlos en los directorios anteriormente mencionados para omitir la ejecución de esta sección*

### 3. Creamos los RDD
En base a los dataset se organizan los datos en diferentes *rdd* para su posterior uso. Los dataset de uso quedarán guardados en el diccionario `rdd_usages` mientras que los dataset de situaciones de las estaciones se lo harán en el otro diccionario `rdd_stations`. Para acceder a los datos se usarán las mismas claves en ambos diccionarios, siendo estas la fecha a consultar en formato `'YYYYMM'`. 

> Por ejemplo, `rdd_usages['201904']` nos proporcionará los datos de uso relativos al mes de Abril del año 2019

### 4. Análisis de los meses disponibles de 2019 
En esta sección se encuentran diversas gráficas y contrastes sobre el uso nocturno del servicio.

### 5. Asesor de ruta BiciMad
Esta sección ofrece una breve interacción con el usuario. Consiste en una breve herramienta que permite introducir una estación de origen y una estación de llegada, así como la hora deseada para realizar el trayecto. Con esos datos se estimará un numero de bicis disponibles en la estación de origen y un número aproximado de puestos libres en la estación destino. 
> **Nota:** esta herramienta está construida pensando en los horarios nocturnos, es por ello que no hay ningun problema realizando viajes alrededor de las 00:00, tendrá en cuenta el cambio de dia para la predicción.

### 6. Ciclos
Como cierre analizaremos los ciclos realizados por los trabajadores.
