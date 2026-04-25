# Changelog - Proyecto Urban Flow

Este archivo documenta los cambios realizados en el proyecto, considerando cada ejercicio como un día de trabajo distinto correspondiente al Sprint 1.

## Ejercicio 01 y 02
- Configuración inicial de la herramienta de versionado (Git) y la rama `sprint_1`.
- Creación de la estructura de directorios (`data/raw`, `data/interim`, `data/processed`).
- Descarga del dataset original histórico (`speeding_fines.csv`).
- Análisis exploratorio inicial: revisión de primeras filas, tipos de datos y conteo de valores nulos.

*Aclaraciones*: realizamos estos puntos inicialmente, al compartir los archivos se presentó el problema de los clones anidados y se reescribió el Ejercicio 1 y 2 a su estructura actual.
Este punto fue el de mayor aprendizaje en el control de versiones, consideramos que la solución actual resuelve los principales problemas del trabajo de versiones con Colab que tiene sus particularidades.
El push del propio notebook se debe hacer no por comando git sino por "File" > "Save a copy in GitHub" ya que no toma los cambios por el guardado automático.

## Ejercicio 03
- Normalización de formatos de fechas y horas (imputación de valores atípicos `1932-01-01` y `00:00`).
- Limpieza y estandarización de strings en ubicaciones y patentes mediante expresiones regulares.
- Eliminación de registros con nulos en columnas relevantes.
- Detección y eliminación de valores atípicos (outliers) en las velocidades registradas utilizando el método de Rango Intercuartílico (IQR).
- Cálculo de variables de negocio: `exceso_velocidad_real` y `exceso_velocidad` (con tolerancia del 5%).
- Filtrado del dataset para conservar únicamente a los verdaderos infractores y guardado del archivo limpio en `interim`.

## Ejercicio 04
- Implementación de la clase `FineAnalyzer` para el análisis estadístico mediante Programación Orientada a Objetos.
- Desarrollo de métodos de clase para obtener: top 5 patentes, top 5 horarios, promedio de excesos (real y reglamentario) y conteo por ubicaciones.

## Ejercicio 05
- Generación de gráficos de análisis visual con Matplotlib.
- Exportación de gráficos de barras (patentes y meses), torta (porcentaje por hora) y líneas (comportamiento de excesos en datos atípicos).
- Archivos guardados exitosamente en `data/interim/plots`.

## Ejercicio 06
- Procesamiento analítico para calcular el porcentaje exacto de infracciones imputadas con la fecha `1932-01-01` y la hora `00:00` sobre el dataset final.

## Ejercicio 07
- Redacción de la conclusión final del análisis de datos.
- Actualización del archivo `Readme.md` incluyendo el objetivo, contexto y conclusiones del Sprint 1.
