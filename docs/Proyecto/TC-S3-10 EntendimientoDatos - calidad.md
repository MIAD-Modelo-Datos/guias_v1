# **Entendimiento de datos - etapa formativa: Calidad de datos**
## **Objetivo**
- Explorar y analizar fuentes de datos (entendimiento de datos) relacionadas con el proyecto del curso. 
- Inspeccionar el nivel de calidad de las fuentes de datos provistas.
- Revisar la viabilidad de implementar análisis con fuentes de datos dadas.
## **Instrucciones**

![](Img/LogoRaSA.png)

RaSA de forma conjunta con un grupo de consultores de inteligencia de negocios, ha trabajado en una especificación de los primeros análisis que quiere que usted realice. En esta primera fase, a partir de estos análisis propuestos, la empresa le ha entregado una serie de fuentes de datos y requiere que usted se focalice en la etapa de calidad de datos que hace parte del entendimiento de datos:

1.	**Análisis de calidad de datos:** Revise las 4 dimensiones de calidad vistas en el curso en las fuentes compartidas y saque conclusiones.

3.  **Socialice con otros grupos:** Valide con otros grupos su resultado y documente los hallazgos encontrados de tal forma que se vaya acercando al entregable de entendimiento de datos que debe entregar la próxima semana. Aprovecha para llevar dudas de la actividad a la sesión sincrónica. En este punto, te recomendamos que sea el líder del proyecto quien se encargue de reportar las inquietudes y garantizar que fueron aclaradas para que puedan realizar con mayor claridad la actividad de entendimiento de datos. 

Recuerde que la exploración de los datos depende de los objetivos que tenga el proyecto de analítica. Es así como RaSA le comparte **ejemplos** de análisis que en este momento está interesado en responder, documentados en la matriz de temas analíticos, donde se encuentra, adicional a los análisis identificados (ver la columna análisis requeridos), los datos requeridos para lograr los objetivos del proyecto.

| Tema analítico  | Análisis requeridos o inferidos | Categoría del análisis (*)  | Procesos de negocio | Fuentes de datos |
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| Comportamiento desleal de proveedores   | **Análisis 1.a:** Dado un proveedor o grupo de proveedores si tiene o ha tenido un comportamiento desleal? <br> **Análisis 1.b:** Dado un rango de fechas se identifican proveedores con comportamientos desleales. Un comportamiento desleal corresponde a proveedores que brinden planes con el mismo tipo de beneficio cuyo valor de copago o coseguro esté por debajo de lo ofrecido por otros proveedores. En particular se evidencian diferencias mayores al 20% permitido, de lo ofrecido por otros proveedores  | Tablero de control  | Oferta de planes  | F2. TiposBeneficios , F3. BeneficiosPlanes  |
| Cobertura de planes | **Análisis 2.a:** Dado un rango de años, mostrar el porcentaje de cobertura de los planes con respecto a las áreas de servicio <br>**Análisis 2.b** ¿Se ha logrado una cobertura total de los proveedores, cubriendo con sus planes TODAS las áreas de servicio? <br>**Análisis 2.c:** ¿Han existido áreas de servicios, a nivel de planes, cubiertas por  menos de dos proveedores?   |Tableros de control | Oferta de planes  | F1. AreasdeServicio, F3. BeneficiosPlanes  |
| Concentraciones de planes |**Análisis 3.a:** Dado un rango de años, identificar ¿cuantos y cuales planes hay por áreas de servicio, estados o condados?<br>**Análisis 3.b:** ¿en qué áreas estados o condados hay concentraciones de planes que no correspondan con la cantidad de habitantes del área/estado/condado?  | Tableros de control |Oferta de planes  | F1. AreasdeServicio, F3. Beneficios planes|
| Evolución de planes | **Análisis 4.a:** Dado un rango de fechas y tipos de beneficios ¿Cómo han evolucionado los costos y tipos de beneficios a lo largo del tiempo por tipo de beneficio, proveedor, fecha? <br>**Análisis 4.b:** ¿Qué tipos de beneficios han aumentado o disminuido costos.| Tableros de control |Oferta de planes  | F2. Tipos Beneficios , F3. Beneficios planes|
 
*La categoría de análisis posibles son Tableros de control, Análisis OLAP, Aprendizaje automático, Consultas SQL. En el curso solo vamos a abordar los tableros de control

** Los análisis de la tabla pueden ser agrupaciones de análisis más pequeños o se pueden extender, incluso puede que los análisis no estén completos. Es libre de proponerle nuevos análisis al negocio o complementar los de la tabla como parte de sus conclusiones. Piense en qué, le beneficiaría más a RaSA y en particular a un usuario que esté interesado en este estilo de análisis.


Para esta actividad de análisis de calidad de datos, la empresa les comparte los siguientes grupos de fuentes de datos en la base de datos RaSaTransaccional:

F1. AreasdeServicio: FuenteAreasDeServicio_Copia_E

F2. TiposBeneficios: FuenteTiposBeneficio_Copia_E

F3. BeneficiosPlanes: FuentePlanesBeneficio_Copia_E  

F4. Tablas de referencia: FuenteCondicionesDePago_Copia_E 

Dichos datos pueden tener errores ya que no han sido utilizados previamente para ser analizados. La empresa se comprometió a compartir más información con ustedes la semana 4 del curso.

## **Recursos requeridos**
***Datos suministrados***

Los datos los pueden encontrar en la base de datos: RaSaTransaccional del servidor que manejamos en los tutoriales. También puede encontrar el diccionario de los mismos [aquí](Diccionario%20I.xlsx), ambos recursos requeridos para el desarrollo de esta tarea. Las tablas compartidas son copias de las tablas transaccionales de la organización. Dado que es posible que sean más de 5 tablas las que se comparten, se recomienda hacer análisis por los grupos de fuentes enumerados previamente.

***Tecnología***

Recuerde que está el tutorial de “Entendimiento de datos”, que será de utilidad para el uso de la tecnología utilizada en esta tarea.
- JupyterLab
- Pyspark

## **Recomendaciones de los entregables**
- Recuerde incluir en la revisión todas las dimensiones de calidad
- Si hay supuestos que debe hacer o preguntas sobre la organización, regístrelos en un archivo para enviarlo más adelante a la organización y pedirles que lo revisen y den una respuesta. 

## **Preguntas o más información**
- Las preguntas que surjan en el desarrollo de esta tarea pueden registrarlas en el slack del curso.
- La forma en que se organicen y aporten al interior del grupo es fundamental para el logro del objetivo del proyecto y será evaluada en la entrega final del proyecto.
