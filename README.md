# herramientas-software-ccc-datos
# Proyecto Urban Flow (Herramientas de software para análisis de datos)

## Sprint 1

### Objetivo
El objetivo principal de este proyecto es aplicar los conocimientos adquiridos
para el versionado de código, la organización, limpieza del código y la
utilización exhaustiva de la librería Pandas para la manipulación de datos.

### Introducción y Contexto
La localidad de Vaalserberg (Bélgica), ubicada en una zona fronteriza,
cuenta con un sistema de radares urbanos para la detección de infracciones
por exceso de velocidad.
Los registros históricos provienen de sistemas heredados que presentan
graves errores de formato y datos faltantes.
El propósito de este sprint es analizar y depurar estos datos para obtener
información fidedigna y preparar el terreno para la migración al nuevo
sistema sin arrastrar inconsistencias.

### Conclusión del Análisis de Datos
Tras procesar el dataset histórico (`speeding_fines.csv`), se concluye que
el sistema heredado carecía de validaciones básicas de entrada.
Se detectó una alta presencia de registros "basura", incluyendo caracteres
especiales en patentes y ubicaciones, así como fallos en los sensores de
tiempo que generaron fechas y horas nulas (estandarizadas durante la
limpieza a `1932-01-01` y `00:00`).

Asimismo, el descubrimiento más relevante a nivel de negocio es que el
sistema viejo guardaba registros de vehículos que **no estaban en infracción**
(velocidades dentro del margen de tolerancia del 5%). Esto se visualizó también
al practicar diversos ejercicios de limpieza donde se observaron valores
negativos en el exceso de velocidad real, eso implicaba que en
realidad no existía tal exceso.
Al aplicar filtros estadísticos (eliminación de outliers vía rango
intercuartílico) y reglas de negocio, se logró depurar la base de datos
para aislar únicamente las verdaderas multas.
El dataset resultante es ahora consistente, confiable y apto para
integrarse al nuevo sistema de detección.

Se realizaron los cambios solicitados por la consigna, finalizando el TP
con un dataset limpio en .csv e imágenes que permiten graficar la situación
del dataset posterior a esa limpieza para su análisis estadístico.

### Integrantes del equipo
Denise Neustadt y Ailén Iglesias Barrera.
CCC Licenciatura de Ciencia de Datos.
Abril 2026.

# Proyecto Urban Flow (Herramientas de software para análisis de datos)

## Sprint 1

### Objetivo
El objetivo principal de este proyecto es aplicar los conocimientos adquiridos
para el versionado de código, la organización, limpieza del código y la
utilización exhaustiva de la librería Pandas para la manipulación de datos.

### Introducción y Contexto
La localidad de Vaalserberg (Bélgica), ubicada en una zona fronteriza,
cuenta con un sistema de radares urbanos para la detección de infracciones
por exceso de velocidad.
Los registros históricos provienen de sistemas heredados que presentan
graves errores de formato y datos faltantes.
El propósito de este sprint es analizar y depurar estos datos para obtener
información fidedigna y preparar el terreno para la migración al nuevo
sistema sin arrastrar inconsistencias.

### Conclusión del Análisis de Datos
Tras procesar el dataset histórico (`speeding_fines.csv`), se concluye que
el sistema heredado carecía de validaciones básicas de entrada.
Se detectó una alta presencia de registros "basura", incluyendo caracteres
especiales en patentes y ubicaciones, así como fallos en los sensores de
tiempo que generaron fechas y horas nulas (estandarizadas durante la
limpieza a `1932-01-01` y `00:00`).

Asimismo, el descubrimiento más relevante a nivel de negocio es que el
sistema viejo guardaba registros de vehículos que **no estaban en infracción**
(velocidades dentro del margen de tolerancia del 5%). Esto se visualizó también
al practicar diversos ejercicios de limpieza donde se observaron valores
negativos en el exceso de velocidad real, eso implicaba que en
realidad no existía tal exceso.
Al aplicar filtros estadísticos (eliminación de outliers vía rango
intercuartílico) y reglas de negocio, se logró depurar la base de datos
para aislar únicamente las verdaderas multas.
El dataset resultante es ahora consistente, confiable y apto para
integrarse al nuevo sistema de detección.

Se realizaron los cambios solicitados por la consigna, finalizando el TP
con un dataset limpio en .csv e imágenes que permiten graficar la situación
del dataset posterior a esa limpieza para su análisis estadístico.

###Corrección de Sprint 1
Se realizaron modificaciones en el ejercicio 03 y 05 de acuerdo a lo observado
por los docentes de la cátedra. Se dejaron a modo de registro del cambio las
celdas originales comentadas.

### Integrantes del equipo
Denise Neustadt y Ailén Iglesias Barrera.
CCC Licenciatura de Ciencia de Datos.
Abril 2026.
