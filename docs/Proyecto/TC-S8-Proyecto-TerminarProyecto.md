# **Terminación, comunicación y evaluación del proyecto final**
## **Objetivo**
- Construir tableros de control para facilitar la interacción con los datos y la identificación de hallazgos útiles para una organización
- Utilizar el resultado de un ejercicio de analítica descriptiva para identificar su utilidad en el contexto de una organización
- Comunicar el resultado de analítica descriptiva a personas de nivel ejecutivo de una organización
- Aplicar una metodología para el desarrollo de proyectos de analítica descriptiva desde el entendimiento de los datos hasta la visualización del resultado
## **Instrucciones**

![](Img/LogoRaSA.png)

En esta fase del proyecto, RaSA desea que trabaje en su grupo para concluir las actividades del proyecto y tener la oportunidad de interactuar con las soluciones de otros grupos, construidas en el curso. 

En particular se espera que realice las siguientes actividades:
1.	***Entregable 1: Tableros de control y descripción de dos análisis.*** Deben proponer dos bocetos de los tableros de control y construir los tableros. Cada tablero de control debe permitir resolver un análisis planteado por ustedes, alineado con los requerimientos de RaSA. El primero de ellos relacionado con las dimensiones (incluido AreasServicios y el hecho de historia de condiciones de tipos beneficio) y otro con los Planes Tipos de Beneficio (la tabla de  HechoPlanesTiposBeneficio y las dimensiones que consideren necesarias). Los tableros deben conectarse a la base de datos que toma el rol de bodega de datos donde están los datos cargados. Para revisar los tableros deben enviar el enlace con la configuración habilitada para **edición**. Recuerden que este último paso se describe en el tutorial de tableros de control. En esta parte, deben documentar los requerimientos en la tabla que se ha utilizado en enunciados previos, donde se incluye, tema analítico, análisis requerido, datos, entre otro, como se muestra en la siguiente tabla.

| Tema analítico  | Análisis requeridos o inferidos | Categoría del análisis (*)  | Procesos de negocio | Fuentes de datos | 
| ------------- | ------------- | ------------- | ------------- | ------------- |  
| Comportamiento desleal de proveedores   | **Análisis 1.a:** Dado un proveedor o grupo de proveedores si tiene o ha tenido un comportamiento desleal? <br>**Análisis 1.b:** Dado un rango de fechas se identifican proveedores con comportamientos desleales. Un comportamiento desleal corresponde a proveedores que brinden planes con el mismo tipo de beneficio cuyo valor de copago o coseguro evidencian diferencias mayores al 20%   | Tablero de control  | Oferta de planes  | F2. Beneficios (Tipos de beneficio y condiciones), F3. BeneficiosPlanes  |

*La categoría de análisis posibles son Tableros de control, Análisis OLAP, Aprendizaje automático, Consultas SQL. En el curso solo vamos a abordar los tableros de control 
** Los análisis de la tabla pueden ser agrupaciones de análisis más pequeños o se pueden extender, incluso puede que los análisis no estén completos. Es libre de proponerle nuevos análisis al negocio o complementar los de la tabla como parte de sus conclusiones. Piense en qué, le beneficiaría más a RaSA y en particular a un usuario que esté interesado en este estilo de análisis. 

2.	***Entregable 2: Video:*** Video para directivos de una organización, de máximo 5 minutos, comunicando el resultado del proyecto, en particular, la interacción con los dos tableros construidos. En este video se espera que apliquen lo visto en el curso, haciendo énfasis en el tema de comunicación (Plantilla de comunicación de tableros de control compartida en la infografía de la semana 7). El video deben dejarlo en este [padlet]([https](https://uniandes.padlet.org/damoreno1972/miad-etrega-proyecto-final-o1xnkslvxqlk88iu)).

3.	***Entregable 3: Coevaluación entre equipos:*** Tendrán la oportunidad de ver el video de otro grupo, al igual que interactuar con los tableros que ese grupo desarrolló como parte de este proyecto. En este punto se espera que pueda darle una retroalimentación valiosa para valorar las fortalezas identificadas en el proyecto y los puntos a mejorar. Esta retroalimentación incluye una calificación. Utilice los criterios definidos de la entrega para asignar esa nota. **Recuerde que el envio para realizar esta actividad la realiza únicamente el líder del grupo**. **Esta actividad debe realizarse dos días después de la entrega del proyecto en el recurso coevaluación entre equipos: entrega final del proyecto**.

4.	***Entregable 4: Coevaluación entre integrantes del equipo:*** Tendrán la oportunidad de reflexionar sobre el trabajo en equipo, realizado en el proyecto y llegar a consensos sobre esa parte. Utilice los criterios definidos de la entrega para asignar esa nota y hacer comentarios.

5. ***Entregable 5: Opcional Bono de 20/100 puntos en la nota de la entrega del proyecto*** En el proyecto, tiene la opción de tener un bono por integración de una nueva fuente de datos. Esta nueva fuente de datos debe aportar datos al modelo multidimensional (si es necesario adáptelo) de igual manera debe estar en el proceso de ETL y debe ser utilizado en alguno de los tableros de control. Debe explicar esta parte e incluirlo en este entregable. Si no hace el bono, en el envío coloque NA (No aplica).

Asociada a esta entrega encuentra un segundo enlace para determinar el grupo al cual le hará la coevaluación entre equipos. De igual manera encontrará un tercer enlace para que de común acuerdo entre los miembros del grupo, evalúen el aporte y compromiso de los distintos integrantes del grupo en lo que denominamos coevaluación entre integrantes del equipo.

## **Recursos requeridos**
Todo el material desarrollado en el curso. Recuerde que estos recursos a nivel de datos y documentación los encuentra en estos enlaces del  repositorio:

●	Datos compartidos en la base de datos **RaSaTransaccional_Tablero**, que corresponden a las tablas que representan el modelo dimensional compartido por RaSA como solución, el cual se presenta en la imagen.

El modelo y la base de datos estarán disponibles después de la entrega de ETL del proyecto.

## **Recomendaciones de los entregables**
- Tener una copia de las tablas compartidas en su ambiente de máquina virtual para que puedan trabajarlas de forma independiente.
- Dividan el proceso de construcción del tablero de control: la primera parte donde adicionan los gráficos y la segunda, donde prueba con la totalidad de los datos. Durante la primera parte, pueden crear una tabla/vista con la misma estructura de la que requieren y una muestra de los registros para entender su comportamiento. Una vez tengan listo y probado el gráfico pueden hacer la consulta sobre la tabla/vista con todos los datos.
    
## **Preguntas o más información**
Las preguntas que surjan en el desarrollo de esta tarea pueden registrarlas en el slack del curso
