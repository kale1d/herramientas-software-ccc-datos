# Urban Flow - Sistema de Radares Urbanos

## Sprint 3: Profesionalización y Persistencia Híbrida

### Objetivo
El objetivo principal  previamente para la gestión de multas por exceso de velocidad.
Se reemplazade este sprint es migrar y profesionalizar la solución
desarrollada el almacenamiento en archivos planos por un esquema de
persistencia híbrido que integra una base de datos relacional (estructurada) y
una base de datos vectorial (semántica), garantizando la escalabilidad del
sistema ante grandes volúmenes de datos y habilitando búsquedas avanzadas.

---

### Introducción y Contexto del Problema
La localidad de Vaalserberg (Bélgica), situada en la región fronteriza con los
Países Bajos y Alemania, cuenta con una red de radares urbanos automáticos
para registrar infracciones por exceso de velocidad. En los sprints previos se
resolvieron los siguientes desafíos del sistema:

1. **Sprint 1 (Depuración de Datos):** Procesamiento de registros provenientes
   de sistemas heredados con graves errores de formato, datos faltantes o
   valores por defecto que daban lugar a registros inconsistentes.
2. **Sprint 2 (Validación de Evidencias):** Vinculación de las actas de multas
   con su correspondiente evidencia visual, identificando que no todas las
   multas poseían imágenes y que existían posibles errores de captura.

En este **Sprint 3**, ante el incremento crítico del volumen de información y
la complejidad operativa, el trabajo manual sobre archivos planos deja de ser
viable. Por este motivo, el desarrollo actual introduce las siguientes capas:

* **Capa Relacional (SQLAlchemy):** Mapeo de los objetos lógicos (Vehículo,
  Radar, Multa y Evidencia) hacia tablas SQLite estructuradas de forma que se
  elimine la redundancia de datos y se resguarde la integridad referencial.
* **Capa Vectorial (ChromaDB + OpenCLIP):** Generación e indexación de
  embeddings a partir de las imágenes de las patentes. Esto habilita una
  arquitectura bimodal capaz de buscar vehículos por aproximación visual en
  la base vectorial y cruzar esos datos con la base relacional en milisegundos.
* **Gobierno de Datos (DVC):** Migración de los archivos binarios pesados
  (imágenes) fuera del control de versiones de Git, delegando su traceo y
  almacenamiento remoto a Data Version Control (DVC).

---

### Requisitos del Entorno e Instalación
Para garantizar que el entorno sea reproducible y ejecute sin errores con la
opción "Ejecutar todo" (Ctrl+F9), el sistema automatiza las dependencias:

```bash
# Instalación de dependencias críticas al inicio del Notebook
pip install -q chromadb open-clip-torch dvc dvc-gdrive

(ratio $\ge$ 80%) permite validar visualmente un porcentaje significativo de
infracciones. Esto dota de integridad legal y probatoria al proceso de cobro,
permitiendo priorizar las auditorías humanas únicamente sobre los casos sin
coincidencia o en estado 'IMPAGA' con evidencias dudosas.
