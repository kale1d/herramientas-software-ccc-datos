# Urban Flow - Sistema de Radares Urbanos
## Sprint 2: Validación de Evidencia Visual

### Objetivo
Desarrollar e implementar un sistema automatizado que determine qué multas
administrativas por exceso de velocidad cuentan con evidencia visual válida
en la localidad de Vaalserberg.

### Introducción y Contexto del Sprint
Los radares urbanos generan registros de multas de forma automática y las
cámaras asocian la evidencia visual. Sin embargo, se presentan desafíos
operativos: no todas las multas tienen imágenes, no todas las imágenes
corresponden a infracciones y existen errores de detección.
Este sprint procesa el dataset del Sprint 1 junto con un banco de imágenes
para realizar una vinculación inteligente mediante procesamiento digital de
imágenes y reconocimiento óptico de caracteres (OCR).

---

### Ejercicio 06: Análisis de Impacto y Relación entre Imágenes y Datos

Al concluir este desarrollo, podemos determinar las siguientes conclusiones
analíticas sobre la relación entre la evidencia visual y los registros estructurados:

* **Naturaleza y Contraste de los Datos:** Existe una clara diferencia entre
los datos administrativos (estructurados, históricos y propensos a la ausencia
de valores o `NaN` por sistemas heredados) y los datos no estructurados
(imágenes de cámaras). La consistencia del sistema depende de un puente de
traducción efectivo, en este caso, el motor OCR y el algoritmo de coincidencia
de cadenas.
* **Efectividad del Pipeline de Imagen (Grises vs. Canny):** Se determinó que
filtros como Canny son ideales para el aislamiento geométrico de contornos
(localizar dónde está la patente), pero destruyen la información tipográfica
esencial que necesitan los modelos de lenguaje visual. Por ello, la conversión
a escala de grises resultó ser el entorno óptimo para extraer texto sólido,
mitigando el ruido cromático sin perder el contraste de los caracteres.
Se probaron las dos opciones y nos inclinamos hacia la escala de Grises.
En Canny nos había dado un total de 411 y en escala de Gises 658.
* **Análisis de la Tasa de Match:** La tasa de coincidencia final expone una
desconexión parcial entre las capturas de las cámaras y el lote de multas del
DataFrame. En ciencia de datos, esto evidencia que los bancos de imágenes del
mundo real suelen representar ventanas temporales específicas o recortes de
auditoría que no necesariamente cubren la totalidad histórica de un sistema
heredado.
* **Impacto Operativo de la Solución:** A pesar de la disparidad de volumen,
la automatización del emparejamiento con un umbral posicional flexible
(ratio $\ge$ 80%) permite validar visualmente un porcentaje significativo de
infracciones. Esto dota de integridad legal y probatoria al proceso de cobro,
permitiendo priorizar las auditorías humanas únicamente sobre los casos sin
coincidencia o en estado 'IMPAGA' con evidencias dudosas.
