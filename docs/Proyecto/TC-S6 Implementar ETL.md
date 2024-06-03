# **Construir un proceso ETL**
## **Objetivo**
- Implementar el proceso ETL del proyecto.  
## **Instrucciones**

![](Img/LogoRaSA.png)

En esta fase del proyecto, a partir de la capacitación recibida en los diferentes temas, algunos ejemplos de análisis requeridos, aclaraciones de la organización sobre los datos compartidos inicialmente y de un modelo multidimensional con manejo de historia propuesto, RaSA considera que están listos para realizar todo lo relacionado con el proceso de ETL. En particular requiere que trabajen en los siguientes entregables:

1. **Entregable 1 - Diseño del ETL:** Incluir el diseño ETL propuesto para poblar las tablas asociadas al modelo multidimensional dado, utilizando como fuentes, las compartidas. Esto incluye manejo de historia. Recuerde incluir la descripción del diseño y utilizar esta [plantilla](PlantillaDiseñoETL.xlsx).
2. **Entregable 2 - Implementación del ETL:** implementación del proceso ETL de las dimensiones y tabla de hechos del proyecto incluyendo manejo de historia.  Recuerde incluir la descripción del proceso de implementación.

A nivel de trabajo en grupo, dada la experiencia que la empresa tiene en este estilo de proyectos, le sugiere lo siguiente:
- Cada miembro del grupo se haga responsable de una dimensión o de dos si la dimensión es básica.
- Definan de forma conjunta el proceso a seguir para las transformaciones y cargue de la tabla de hechos
- El miembro con las dimensiones más sencillas o el menor número de dimensiones asignadas trabaje la tabla de hechos. 

## **Recursos requeridos**
***Datos suministrados***

Los datos los puede encontrar en la base de datos: RasaTransaccional_ETL del servidor que manejamos en los tutoriales. También puede encontrar el diccionario de los mismos [aquí](Diccionario%20I.xlsx), ambos recursos requeridos para el desarrollo de esta tarea. Las tablas son copias de las tablas fuente del proceso que se está analizando. 
Recuerde que los datos que se usaron para el entendimiento de datos tienen como sufijo Copia (e.g., BeneficiosCopia), en caso de que deseen repasar o rehacer el ejercicio de Entendimiento de datos. 
Los datos revisados por RaSA a partir de los resultados y/o conclusiones que obtuvieron en la etapa de entenimiento de datos y que deben ser utilizados en el proceso de ETL quedan en las tablas:
- F1: GruposAreasdeServicio y AreasDeServicio
- F2: Beneficios
- F3: BeneficiosPlanes
- F4: NivelDeRed y CondicionesDePago 

En el proceso de carga, para manejar atributos tipo fecha, si el atributo no tiene día o mes, asuma como valores por defecto el primer día del mes, y el primer mes de cada año.

***Respuestas del negocio a conclusiones de Entendimiento***

RaSa le comenta que las respuestas estarán disponibles después de la entrega del modelado.


***Modelo multidimensional propuesto***<br>

RaSa le comenta que las respuestas estarán disponibles después de la entrega del modelado.


***Tecnología***

Recuerden que están los tutoriales "Proceso ETL" y "Proceso ETL Incremental"

## **Recomendaciones de los entregables**
* Seguir las indicaciones del tutorial de ETL
* Ser cuidadosos al momento de cargar la tabla de hechos

## **Preguntas o más información**
- Si el cargue de datos con la función <i>guardar_db()</i> se demora, hacer uso del código de cargue por lotes que encuentra en el Tutorial de ETL al final del bloque 6: Hecho orden
- Recuerde que puede hacer reemplazos de cadenas de caracteres haciendo uso de diccionarios, puede encontrar ejemplos en el siguiente enlace: https://sparkbyexamples.com/pyspark/pyspark-replace-column-values/
- Las preguntas que surjan en el desarrollo de esta tarea pueden registrarlas en el slack del curso

