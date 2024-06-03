| Tema analítico  | Análisis requeridos o inferidos | Categoría del análisis (*)  | Procesos de negocio | Fuentes de datos |
| ------------- | ------------- | ------------- | ------------- | ------------- | 
| Comportamiento desleal de proveedores   | **Análisis 1.a:** Dado un proveedor o grupo de proveedores si tiene o ha tenido un comportamiento desleal? <br>**Análisis 1.b:** Dado un rango de fechas se identifican proveedores con comportamientos desleales. Un comportamiento desleal corresponde a proveedores que brinden planes con el mismo tipo de beneficio cuyo valor de copago o coseguro evidencian diferencias mayores al 20%   | Tablero de control  | Oferta de planes  | F2. Beneficios (Tipos de beneficio y condiciones), F3. BeneficiosPlanes  |
| Cobertura de planes | **Análisis 2.a:** Dado un rango de años, mostrar el nivel de cobertura de los planes con respecto a las áreas de servicio, <br>**Análisis 2.b** ¿Se ha logrado una cobertura total de los proveedores, cubriendo con sus planes TODAS las áreas de servicio? <br>**Análisis 2.c:** ¿Han existido áreas de servicios que sean cubiertas, a nivel de planes, por  menos de dos proveedores?   |Tableros de control | Oferta de planes  | F1. GruposAreasdeServicio y areas de servicio, F3. BeneficiosPlanes  |
| Concentraciones de planes |**Análisis 3.a:** Dado un rango de años, identificar ¿cuantos y cuales planes hay por áreas de servicio, estados o condados?<br>**Análisis 3.b:** ¿en qué áreas estados o condados hay concentraciones de planes que no correspondan con la cantidad de habitantes del área/estado/condado.  | Tableros de control |Oferta de planes  | F1. GruposAreasdeServicio y areas de servicio, F3. Beneficios planes|
| Evolución de planes | **Análisis 4.a:** Dado un rango de fechas y tipos de beneficios ¿Cómo han evolucionado los costos y tipos de beneficios a lo largo del tiempo por tipo de beneficio, proveedor, fecha? <br>**Análisis 4.b:** ¿Qué tipos de beneficios han aumentado o disminuido costos.| Tableros de control |Oferta de planes  | F2. Beneficios (Tipos de beneficio y condiciones), F3. Beneficios planes|
 
*La categoría de análisis posibles son Tableros de control, Análisis OLAP, Aprendizaje automático, Consultas SQL. En el curso solo vamos a abordar los tableros de control

** Los análisis de la tabla pueden ser agrupaciones de análisis más pequeños o se pueden extender, incluso puede que los análisis no estén completos. Es libre de proponerle nuevos análisis al negocio o complementar los de la tabla como parte de sus conclusiones. Piense en qué, le beneficiaría más a RaSA y en particular a un usuario que esté interesado en este estilo de análisis.


F1. AreasdeServicio: FuenteAreasDeServicio_Copia_E

F2. TiposBeneficios: FuenteTiposBeneficio_Copia_E

F3. BeneficiosPlanes: FuentePlanesBeneficio_Copia_E

F4. Tablas de referencia: FuenteCondicionesDePago_Copia_E
