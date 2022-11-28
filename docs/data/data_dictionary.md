# Data Dictionary

Después de extraer los datos númericos de las imagenes satelitales obtenemos un archivo anual con valores diarios. Sin embargo, se hace la distinción que aunque hablamos de la cuenca del Guaviare, está se encuentra dividida en 4 áreas.

1. AMEM: Área de manejo especial de La Macarena
2. ARIARI: Río Ariari
3. GUAYABERO: Río Guayabero
4. GUAVIARE: La cuenca completa, esto es el área general. 

Ambas bases de datos a utilizar necesitan de esta distinción puesto que se tiene un dato para cada área. 

# Database: Precipitación 

Consiste en varios archivos. Un archivo por año, cada archivo tiene un dato por día del año de precipitación (en milimetros) por cada una de las áreas descritas anteriormente. 

![UML Diagram](/file/uml/database1)

## Table 1

| column | type | description |
| --- | --- | --- |
| FECHA | DATE | 1986-11-22 |
| AMEM | FLOAT | 8.417908874 |
| ARIARI | FLOAT | 8.417908874 |
| GUAYABERO | FLOAT | 8.417908874 |
| GUAVIARE | FLOAT | 8.417908874 |


# Database: Deforestación

Consiste en varios archivos. Un archivo por año, cada archivo tiene un dato por día del año de deforestación (% de perdida de cobertura de masa vegetal) por cada una de las áreas descritas anteriormente. 

![UML Diagram](/file/uml/database1)

## Table 2

| column | type | description |
| --- | --- | --- |
| FECHA | DATE | 1986-11-22 |
| AMEM | FLOAT | 0.322345765|
| ARIARI | FLOAT | 0.322345765 |
| GUAYABERO | FLOAT | 0.322345765 |
| GUAVIARE | FLOAT | 0.322345765 |
