# **Modelo dimensional del proyecto y diseño del proceso ETL**
## **Objetivo**
- Modelar multidimensionalmente la base datos (BD) utilizada para los análisis sugeridos del proyecto.  
- Diseñar el proceso ETL para cargar las tablas que se deben crear asociadas al modelo multidimensional propuesto.
## **Instrucciones**

![](Img/LogoRaSA.png)


En esta fase del proyecto, a partir de los análisis requeridos y de fuentes de datos proporcionadas, Infraestructura Visible le solicita:
1.	**Entregable 1- Modelo multidimensional:** Una propuesta de modelo multidimensional que incluya historia de los atributos de dimensiones, permita realizar la mayoría de los análisis propuestos e involucre los datos de las fuentes compartidas que permitirán realizar no solo los análisis propuestos si no otros en el futuro, acompañado de una descripción y justificación del mismo. Suponga como proceso de negocio <i>OfertaPlanes</i> que se realiza de forma anual.
2.	**Entregable 2 - Diseño del proceso ETL:** Incluir el diseño ETL propuesto para poblar las tablas asociadas al modelo multidimensional propuesto, utilizando como fuentes, las compartidas y la esta [plantilla](PlantillaDiseñoETL.xlsx). Incluya una descripción general con los elementos que considere son importantes para la comprensión del diseño.

A continuación, se presentan los análisis propuestos y los datos requeridos para lograr los objetivos de esta tarea.

| Tema analítico  | Análisis requeridos o inferidos | Categoría del análisis (*)  | Procesos de negocio | Fuentes de datos |
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| Comportamiento desleal de proveedores   | **Análisis 1.a:** Dado un proveedor o grupo de proveedores si tiene o ha tenido un comportamiento desleal? <br>**Análisis 1.b:** Dado un rango de fechas se identifican proveedores con comportamientos desleales. Un comportamiento desleal corresponde a proveedores que brinden planes con el mismo tipo de beneficio cuyo valor de copago o coseguro evidencian diferencias mayores al 20%   | Tablero de control  | Oferta de planes  | F2. Beneficios (Tipos de beneficio y condiciones), F3. BeneficiosPlanes  |
| Cobertura de planes | **Análisis 2.a:** Dado un rango de años, mostrar el nivel de cobertura de los planes con respecto a las áreas de servicio, <br>**Análisis 2.b** ¿Se ha logrado una cobertura total de los proveedores, cubriendo con sus planes TODAS las áreas de servicio? <br>**Análisis 2.c:** ¿Han existido áreas de servicios que sean cubiertas, a nivel de planes, por  menos de dos proveedores?   |Tableros de control | Oferta de planes  | F1. GruposAreasdeServicio y areas de servicio, F3. BeneficiosPlanes  |
| Concentraciones de planes |**Análisis 3.a:** Dado un rango de años, identificar ¿cuantos y cuales planes hay por áreas de servicio y estados o condados? , <br>**Análisis 3.b:** ¿en qué áreas, estados o condados hay concentraciones de planes que no correspondan con la cantidad de habitantes del área?  | Tableros de control |Oferta de planes  | F1. GruposAreasdeServicio y areas de servicio, F3. Beneficios planes|
| Evolución de planes | **Análisis 4.a:** Dado un rango de fechas y tipos de beneficios ¿Cómo han evolucionado los costos y tipos de beneficios a lo largo del tiempo por tipo de beneficio, proveedor, fecha? <br>**Análisis 4.b:** ¿Qué tipos de beneficios han aumentado o disminuido costos.| Tableros de control |Oferta de planes  | F2. Beneficios (Tipos de beneficio y condiciones), F3. Beneficios planes|
 
*La categoría de análisis posibles son Tableros de control, Análisis OLAP, Aprendizaje automático, Consultas SQL. En el curso solo vamos a abordar los tableros de control

** Los análisis de la tabla pueden ser agrupaciones de análisis más pequeños o se pueden extender, incluso puede que los análisis no estén completos. Es libre de proponerle nuevos análisis al negocio o complementar los de la tabla como parte de sus conclusiones. Piense en qué, le beneficiaría más a RaSA y en particular a un usuario que esté interesado en este estilo de análisis.

** Los análisis de la tabla pueden ser agrupaciones de análisis más pequeños o se pueden extender, incluso puede que los análisis no estén completos. El objetivo de compartir esos análisis es brindar una guía de lo que la organización le gustaría lograr con el proyecto.

## **Recursos requeridos**
***Datos suministrados***

Los datos los puede encontrar en la base de datos: ProyectoTransaccional del servidor que manejamos en los tutoriales. También puede encontrar el diccionario de los mismos [aquí](Diccionario%20I.xlsx), ambos recursos requeridos para el desarrollo de esta tarea. Las tablas compartidas por grupo de fuente son:

F1. AreasdeServicio: FuenteAreasDeServicio_Copia_E

F2. TiposBeneficios: FuenteTiposBeneficio_Copia_E

F3. BeneficiosPlanes: FuentePlanesBeneficio_Copia_E

F4. Tablas de referencia: FuenteCondicionesDePago_Copia_E

***Respuestas del negocio a conclusiones de Entendimiento***

Después de hacer una revisión a las fuentes que fueron inicialmente proporcionadas, gracias a sus comentarios y preguntas, encontramos los siguientes errores relacionados con las reglas de negocio que les compartimos:

1.	Las áreas de servicio NO cubren todos los condados del país.
2.	No fue posible validar la condición de límites cuantitativos, así que, si se evidencia límites cuantitativos sin valor o con un valor en cero, en los planes que los ofrecen, debe colocar como valor por defecto 333 para poder identificar el error y corregirlo en el futuro.
3.	Se corrigió la fecha de 1800 que estaba en la fuente de áreas de servicio.
4.	La fuente de áreas de servicio tenía información solo de los años 2017 y 2018 y faltaba todo el año 2019. 
5.	En la fuente de tipos de beneficios no deberían existir diferentes condiciones y unidad de límite para el mismo tipo de beneficio en el mismo año. Esto fue arreglado y solo debe existir un valor de condiciones y unidad límite de tipo de beneficio por año.
6.	El valor máximo Copago y Coseguro para el año 2018 es 3500 y 100 respectivamente.
7.	En la fuente de condiciones de pago se eliminaron los registros con el mismo tipo y descripción que tenía diferentes identificadores.

RaSa también le comenta que:

1.	En la fuente de planes beneficio
a.	Se corrigieron los registros que tenían valores nulos en IdPlan, IdTipoBeneficio o IdAreaDeServicio. 
b.	Se eliminaron los registros con IdTipoBeneficio que no estaban en la fuente de Tipos de Beneficios. Sin embargo, todavía existen IdAreaDeServicio que no están presentes en la fuente correspondiente, por lo que se le recomienda crear un registro de desconocido (Identificador=0) y NO omitir esta información en el proceso de carga. 
c.	Finalmente, las fechas inválidas fueron actualizadas, pero todavía existen fechas con otro tipo de formato y se le pide que las transforme para que todas queden con formato YYYY-MM-DD.

2.	En la fuente de tipos de beneficio
a.	Se corrigieron los registros con diferentes unidades de límites para el mismo beneficio en el mismo año. 
b.	Sin embargo, siguen existiendo errores de consistencia en los valores de las condiciones, se le pide cambiar los diferentes valores para que queden únicamente “Yes” y “No”.

3.	En la fuente de áreas de servicio
a.	Se eliminaron los registros con diferentes IdGeografia cuyo contenido en los demás atributos era el mismo. 
b.	Se corrigieron los registros con IdAreaDeServicio e IdGeografia nulos. 
c.	Las fechas erróneas fueron actualizadas por las correctas. 
d.	Se le pide corregir los registros con áreas negativas, multiplicando por -1 esos valores.
e.	Finalmente, los que presentan un error de digitación en la población actual con 3 ceros y un uno al final del número (0001) debe corregirlos y quitarles estos últimos 4 dígitos, de tal forma que si el valor era 27540001 debe quedar 2754.

4.	En la fuente de condiciones de pago
a.	Se actualizaron los registros con tipo NaN 
b.	Sin embargo, siguen existiendo errores de consistencia, se le pide corregir el tipo a solo Copago y Coseguro.
5.	Puede que existan todavía duplicados de los registros en las fuentes, por favor revisar y eliminarlos.
6.	Estaremos atentos si quedaron preguntas sin contestar para hacerlo en la menor brevedad.

***Tecnología***

Recuerde los videos y lecturas de modelado multidimensional, que serán de utilidad para el desarrollo de esta tarea. En particular los de errores frecuentes. Este último le permitirá validar y mejorar la calidad de su modelo.

Adicionalmente, se le sugiere utilizar una herramienta como [GenMyModel](https://www.genmymodel.com/) o [Lucidchart](https://lucid.app/es/users/login#/login?_gl=1*1sru4v4*_ga*MjA1NjkyODI5LjE2NTUzMjA2MzY.*_ga_MPV5H3XMB5*MTY1NTQzMTAyOS4yLjAuMTY1NTQzMTAyOS42MA..&anonId=0.8bb37e0e18168cc6c65&sessionDate=2022-06-17T01:57:06.970Z&sessionId=0.88d2ce41816f60d91a&activate=lucidchart) para dibujar el modelo. Este tipo de herramientas facilita el mantenimiento de los modelos de datos.

## **Recomendaciones de los entregables**
- Recuerde que el modelo de datos no solo es para resolver los análisis actuales. Haga un balance entre lo proporcionado por las fuentes y los tipos de análisis que tiene hasta este momento para proponer su modelo.
## **Preguntas o más información**
- Las preguntas que surjan en el desarrollo de esta tarea pueden registrarlas en el slack del curso
