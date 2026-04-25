# Changelog - Proyecto Urban Flow

Este archivo documenta los cambios realizados en el proyecto, considerando cada ejercicio como un día de trabajo distinto correspondiente al Sprint 1.

## Ejercicio 01 y 02
- Configuración inicial de la herramienta de versionado (Git) y la rama `sprint_1`.
- Creación de la estructura de directorios (`data/raw`, `data/interim`, `data/processed`).
- Descarga del dataset original histórico (`speeding_fines.csv`).
- Análisis exploratorio inicial: revisión de primeras filas, tipos de datos y conteo de valores nulos.

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

## Punto 05
- Generación de gráficos de análisis visual con Matplotlib.
- Exportación de gráficos de barras (patentes y meses), torta (porcentaje por hora) y líneas (comportamiento de excesos en datos atípicos).
- Archivos guardados exitosamente en `data/interim/plots`.

## Punto 06
- Procesamiento analítico para calcular el porcentaje exacto de infracciones imputadas con la fecha `1932-01-01` y la hora `00:00` sobre el dataset final.

## Punto 07
- Redacción de la conclusión final del análisis de datos.
- Actualización del archivo `Readme.md` incluyendo el objetivo, contexto y conclusiones del Sprint 1.
