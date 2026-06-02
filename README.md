# Proyecto - Data Analytics V3 - Unidad 4 - Dashboard Análisis de Datos
Proyecto correspondiente a la unidad 4 Dashboard y Análisis de Datosdel curso Data Analytics V3
El objetivo del proyecto es realizar un análisis exploratorio de datos y representarlo mediante un dashboard interactivo, utilizando Excel o Google Sheets.

## 1.Estructura del proyecto

README.md

Proyecto unidad 4 - Rendimiento en exámenes.xlsm - Copia del ejercicio en .xlsm

StudentPerformanceFactors BRUTO.csv - Datos en bruto (tal cual se han descargados de la fuente correspondiente)

## 2.Origen de los datos
Los datos utilizados en este proyecto corresponde a una base de datos sobre factores influyentes en el rendimiento académico de estudiantes.
El conjunto de datos consta de 6.607 filas y 20 columnas, incluyendo datos cuantitativos y cualitativos.

- Plataforma fuente: Kaggle  
- Nombre de la base de datos: Student Performance Factors  
- Enlace: https://www.kaggle.com/datasets/lainguyn123/student-performance-factors
- Formato de descarga .csv (formato de texto)

## 3. Análisis descriptivo de los datos

- Hours_Studied: Media de horas que ha estudiado cada alumno por semana
- Attendance: Porcentaje de clases asistidas 
- Parental_Involvement: Nivel al que los padres han estado involucrados en los estudios de los hijos (Low, Medium, High)
- Access_to_Resources: Acceso a recursos educativos.  (Bajo, Medio, Alto)
- Extracurricular_Activities: Participación en actividades extraescolares (Si, no)
- Sleep_Hours: Media de horas de sueño por la noche
- Previous_Scores: Media de resultados obtenidos en examenes anteriores
- Motivation_Level: Nivel de motivación del estudiante (Bajo, Medio, Alto)
- Internet_Access: Disponibilidad de acceso a internet (Sí, No)
- Tutoring_Sessions: Número de sesiones de tutoría asistidas al mes
- Family_Income: Nivel de ingresos familiares (Bajo, Medio, Alto)
- Teacher_Quality: Calidad del profesor (Bajo, Medio, Alto)
- School_Type: Tipo de colegio (Público o privado)
- Peer_Influence: Influencia del grupo de iguales en el rendimiento académico (Positiva, Neutral, Negativa)
- Physical_Activity: Número medio de horas de actividad física por semana.
- Learning_Disabilities: Dificultades de aprendizaje (Sí, No)
- Parental_Education_Level: ivel educativo más alto alcanzado por los padres (Secundaria, Universidad, Posgrado)
- Distance_from_Home: Distancia del domicilio al centro educativo (Cerca, Media, Lejos)
- Gender: Género del estudiante (Masculino, Femenino)
- Exam_Score: Puntuación final del examen


Variable Target: Calificación de examen (dato de tipo numérico)

Datos de tipo numéricos

- Horas de estudio (total de horas de estudio)
- Asistencia (porcentaje de asistencia)
- Horas de sueño (número de horas de sueño)
- Calificación previa (número de 0 a 100)
- Sesiones de tutoría (cantidad de sesiones de tutoría)
- Actividad de física 

Datos de tipo categórico

- Involucramiento de padres (bajo, medio, alto)
- Acceso a recursos (bajo, medio, alto)
- Motivación (baja, media, alta)
- Acceso a Internet (si, no)
- Ingreso económico familiar (bajo, medio, alto)
- Calidad de la enseñanza (baja, media, alta)
- Tipo de escuela (pública, privada)
- Influencia del grupo (negativa, neutral, positiva)
- Discapacidad de aprendizaje (no, si)
- Nivel educativo de los padres 
- Distancia hogar-centro educativo (cerca, moderada, lejos) 
- Género (masculino, femenino)


## 4. Limpieza de datos

Se ha utilizado la fórmula CONTAR.BLANCO(rango) para la detección de valores faltantes, replicando dicha fórmula en cada columna para entender en qué categoría se registra la falta de valores. 
Como resultado de este análisis, se ha observado:

- Variable Teacher_Quality: 78 valores faltantes
- Variable Parental_Education_Level: 90 valores faltantes
- Variable Distance_from_Home: 67 valores faltantes

 Para tomar una decisión respecto a cómo se procederá con la transformacion de estos valores, es importante observar los valores posibles para cada una de estas variables:

- Variable Teacher_Quality: Low, Medium, High
- Variable Parental_Education_Level: College, High School, Postgraduate
- Variable Distance_from_Home: Near, Moderate, Far

Se obsrva entonces, que en el caso de las variables  Teacher_Quality y de Distance_from_Home, se pueden rellenar estos valores faltantes con el valor intermedio o moderado. 
En el caso de la variable Parental_Education_Level, sin embargo, no sería posible completar estos valores utilizando un valor medio, por lo que, para considerar la posibilidad de descartar estas lineas, se calcula cuál sería el impacto de hacerlo.
Al tratarse de 90 líneas, representa el 1,36% de las 6606 lineas de la base de datos. Considerando que es un porcentaje muy pequeño de los datos, se ha decidido descartar estos datos. 
Al descartarse las filas mencionadas, nuestra tabla queda con un total de 6516 filas, y se ha procedido a completar los valores faltantes de las otras dos variables con los valores intermedios.
Para realizarlo, se ha utilizado la función Reemplazar.

Dentro de la identificación de variables, se ha procedido a realizar una tabla dinámica con los valores estadísticos principales de nuestra variable target, agregando un gráfico de cajas y bigotes para visualizarlo mejor. 
Al realizarlo, se ha detectado un outlier, que posee un valor no válido en nuestra escala (mayor a 100). Teniendo en cuenta esto, se ha considera suprimir dicha linea de nuestra tabla, para dar mayor confiabilidad a nuestro análisis.


## 5. Análisis de datos

Se puede observar la variable Previous_Scores en nuestra tabla. Teniendo en cuenta la misma, se generan nuevas columnas en nuestra tabla, correspondiente a la Evolución de los estudiantes en porcentaje del examen anterior al examen, cuyas calificaciones son nuestra variable target; y la variable Descripción de dicha Evolución, clasificando los estudiantes entre aquellos que han mejorado, aquellos que han empeorado y aquellos que han mantenido.

En primera instancia se realiza un análisis global de nuestra variable target. Para ello, se realiza una tabla dinámica donde se organizan las califaciones en rangos, y se muestra la cantidad de estudiantes en cada rango.

A partir de allí, se realiza un análisis de lo que considero los Big Numbers de nuestro proyecto, incluyendo el comportamiento de la evolución de los estudiantes respecto al examen anterior.

A continuación, se calcula el coeficiente de correlación entre las variables numéricas que tenemos en nuestra tabla, y nuestra variable target.
  De acuerdo a los valores obtenidos, se observa la influencia de cada una de estas variables. Se realiza un análisis focalizado en aquellas con influencia significativa.

Además, se analiza la influencia de los factores socioeconómicos en el rendimiento de los exámentes. Para cada uno de ellos se realiza la tabla dinámica correspondiente y su gráfico asociado.

 ## 6. Dashboard  
 
   El dashboard presenta en primera instancia un grupo de Big Numbers. Entre ellos se encuentran la cantidad de estudiantes, el puntaje promedio del exámen correspondiente a nuestra variable target, el puntaje promedio en el exámen previo , el porcentaje de estudiantes que ha mejorado su nota y el porcentaje que ha empeorado su nota.
   
   Se incluyen los siguientes gráficos de análisis:
   
     -  I) Se dividen las calificaciones por rangos, y se distribuyen los estudiantes según dichos rangos de calificaciones.
     -  II) Evolución respecto al último examen (porcentaje de estudiantes).
     -  III) Calificación promedio según porcentaje de asistencia organizado por rangos. La linea correspondiente al eje secundario corresponde a la cantidad de estudiantes.
     -  IV) Calificación promedio según cantidad de horas de estudio organizadas por rangos. La linea correspondiente al eje secundario corresponde a la cantidad de estudiantes.
     -  V) Calificación promedio según cantidad de horas de actividad física medias por semana organizadas por rangos. La linea correspondiente al eje secundario corresponde a la cantidad de estudiantes.
     -  VI) Calificación promedio según cantidad de sesiones de tutorías. La linea correspondiente al eje secundario corresponde a la cantidad de estudiantes.
   
   Se agregas filtros de segmentación de datos conectados a estos gráficos. Los filtros corresponden al Nivel de Motivacion, Involucramiento de Padres, Calidad de Enseñanza, Influencia de Compañeros, Género, Nivel Educativo de Padres, Acceso a Recursos, Ingreso Familiar, Acceso a Internet y Tipo de Escuela.

   Además, se incluye dos botones de comandos que activan macros para obtener la información de los gráficos menciones (excepción gráfico II) del exámen presente o del examen anterior según corresponda. Esto nos permite observar el comportamiento de nuestra variable para cada una de las situaciones.
     

  ## 7. Conclusiones
  
  La calificación media es de 67,23 con una desviación estandar del 5,77%, es decir, un valor de 3,88. Esta calificación media muestra un decrecimiento de un 10,47% con respecto a la califación promedio del examen anterior, con un valor de 75,09.
  
  El porcentaje de asistencia tiene un coeficiente de correlación del 0,585 y es el factor más influyente. Se observan aproximadamente 6 puntos de diferencia entre aquellos alumnos con menos de 60% asistencia, y aquellos con una asistencia mayor al 90%.
  
  La cantidad de horas de estudio es el segundo factor más influyente, con un coeficiente de correlación de 0,44. Se pueden ver 7 puntos de diferencia entre aquellos estudiantes con menos de 10 horas de estudio, y aquellos con mas de 30 horas de estudio.
  
  Las sesiones de tutoría tambien muestra una correlación positiva con el rendimiento de los estudiantes en el exámen.
  
  Los factores socioeconómicos como el acceso a recursos y la educación de los padres, muestra una influencia menor pero claramente visible. 
