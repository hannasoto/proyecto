# Project Charter

## Entendimiento del negocio

* Cliente y dominio:
El cliente al que va dirigido es a una consultora ambiental con interés en el efecto de la erradicación de los cultivos ílicitos en una zona de reserva de parques naturales en la cuenca del Guaviare.
* Problema:
Se busca evaluar el cambio númerico a futuro de las variables de precipitación y de la deforestación con la situación actual de los cultivos ílicitos sobre la zona de interes. Es una herramienta útil para tomadores de decisión frente al manejo de dichos cultivos y la normativa respectiva. 

## Alcance
* Soluciones de Ciencia de datos a construir:
En primer lugar se quiere hacer pronóstico en ambas variables para poder tomar decisiones frente a la mitigación de impactos. Adicionalmente, se busca entender la asociación entre las dos variables ambientales. 
Por otro lado, entender los patrones del efecto de la deforestación en el área.
* Que se hará?
Modelo de deep learning para pronóstico con series de tiempo de variables ambientales. 
A partir de la identificación de los fenomenos de deforestación y el efecto en el área (en términos de precipitación) historicamente, clasificar en que parte de la cuenca se vería el efecto. 
* Como será consumido por el cliente?


## Personal
* Who are on this project:
		* Project lead
		* PM
		* Data scientist(s)
	* Client:
		* Ingeniero Ambiental encargado del proyecto en la consultora
		* Administración consultora
	
## Metricas
* Objetivos cualitativos: Entender el efecto a largo plazo de la deforestación por cultivos ílicitos. 
* Metrica cuantificable:  La disminución cuantitativa en la precipitación a modo de pronóstico. 
* Mejora cuantificada en los valores para el cliente: Disminución del 10% del agua disponible en el área para un periodo de menos de 5 años.
* Valor actual de la metrica: -
* Como se hará medición de la metrica? Pronóstico a partir de series de tiempo en un periodo de 10 años.

## Plan
* Fases: 

Extracción de datos: requiere de extracción de la información a partir de NETcdfs en corridas anuales. Para precipitación y deforestación. 

Asociación de datos a diferentes áreas de las cuencas (cuenca arriba, cuenca abajo, municipio x y municipio y, zona de reserva) para encontrar su efecto.

Procesamiento de los datos: Arreglos y demás, por variables se deben hacer promedios multianuales o encontrar la mejor manera de eliminar el ruido de las series de tiempo. 

Exploración de los datos: encontrar la asociación estadistica entre las dos variables principales y las áreas. 

Extraer la información y limpiar la base de datos.

Modelado a partir de MLE: modelos para series de tiempo. 

Evaluación: evaluación del modelo y comparación con lo que ha sucedido hasta la actualidad para entender el pronostico.

Entrega al cliente.

## Arquitectura
* Data
  * De dónde vienen los datos?
  Imagénes satelitales de la cuenca del guaviare que permiten identificar los valores de precipitación y deforestación promedio para el área en cada día en un período de 1986 a 2017. 
  Shapes de la data geografica abierta de Colombia de la cuenca del Guaviare para poder cortar las imagenes y delimitarlas. 
  
* Data movement from on-prem to Azure using ADF or other data movement tools (Azcopy, EventHub etc.) to move either
  * all the data, 
  * after some pre-aggregation on-prem,
  * Sampled data enough for modeling 

* Que herramientas se utilizaran y fuentes de almacenamiento de datos y analitica para la solución.
En este caso se usa ArcGis para poder delimitar las imagenes satelitales y realizar el procesamiento de las imagenes con el fin de extraer los datos númericos que se necesitan. 
Posteriormente, en R se hacen los análisis que permiten extraer los archivos .csv de los valores de precipitación y deforestación diarios para todos los años. 
Los primeros análisis multivariados y univariados se haráne en python. 
* How will the score or operationalized web service(s) (RRS and/or BES) be consumed in the business workflow of the customer? If applicable, write down pseudo code for the APIs of the web service calls.
  * How will the customer use the model results to make decisions
  * Data movement pipeline in production
  * Make a 1 slide diagram showing the end to end data flow and decision architecture
    * If there is a substantial change in the customer's business workflow, make a before/after diagram showing the data flow.

## Communicación
* Como nos comunicaremos? 
Semanalmente se haran reuniones por TEAMS entre los dos equipos (cliente y nosotros)
Comunicación abierta por slack para el equipo. 2 reuniones semanales para verificar plan y avances. 
