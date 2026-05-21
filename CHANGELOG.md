# Changelog - Grupo 18

## [Sprint 2] - Día 1
### Añadido
- Inicialización del entorno del Sprint 2 a partir de la rama 'sprint_1'.
- Descarga y descompresión automatizada del dataset de imágenes de patentes.

## [Sprint 2] - Día 2
### Añadido
- Clasificación de imágenes en los grupos 'plates' y 'completes' mediante
análisis de dimensiones y nombres.
- Exportación del diccionario estructurado intermedio a 'group_images.json'.
- Función reutilizable de visualización aleatoria usando subplots de Matplotlib.

## [Sprint 2] - Día 3
### Añadido
- Pipeline de procesamiento digital de imágenes: conversión a escala de grises,
suavizado Gaussiano (5x5) y detector de bordes Canny.
- Almacenamiento organizado de las matrices procesadas en el directorio interim.

## [Sprint 2] - Día 4
### Añadido
- Integración del motor EasyOCR enfocado sobre la capa de escala de grises para
 lectura de caracteres.
- Desarrollo de la función 'match_strings' para verificación posicional de
texto con tolerancia al ruido y umbral del 80%.
- Cruce de datos y exportación del DataFrame final consolidado en
'speeding_fines_image.csv'.

## [Sprint 2] - Día 5
### Añadido
- Cuantificación analítica de métricas del negocio (multas sin foto, estados
de pago y consistencia).
- Integración de conclusiones de impacto de datos en la documentación técnica
del repositorio.
