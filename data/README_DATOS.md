# Datos del proyecto

> Por motivos de **confidencialidad institucional**, los archivos de datos originales **no se incluyen** en este repositorio.

## Archivos esperados (no publicados)

| Archivo | Filas | Descripción |
|---|---|---|
| `1_Creditos_EstudiantesREV.xlsx` | 191.130 | Notas débito de créditos educativos UAO 2015-2025 |
| `2_Cartera_depuradaREV.xlsx` | 18.453 | Cartera vigente con saldos y edades de mora |

## Fuente

**Departamento de Apoyo Financiero a Estudiantes — Universidad Autónoma de Occidente (UAO)**

Acceso autorizado únicamente con fines académicos en el marco de la Maestría en Ciencia de Datos de la Pontificia Universidad Javeriana Cali.

## Marco legal

El tratamiento de los datos personales se rige por la **Ley 1581 de 2012** (Protección de Datos Personales en Colombia) y la política institucional de la UAO.

Los identificadores `Cliente` e `ID_Estudiante` que aparecen en el sistema son **códigos numéricos internos**; no se publica información personal directa (nombres, documentos, contactos).

## Solicitud de acceso

Investigadores con interés legítimo pueden solicitar acceso a través del:

- Departamento de Apoyo Financiero — UAO
- Persona enlace institucional: Roberto Arango Delgado (Vicerrector Administrativo y Financiero)

## Outputs publicados

Los archivos en la carpeta `outputs/` son resultados **agregados y/o anonimizados** generados por el notebook. No contienen identificadores personales reidentificables más allá de los códigos internos.

## Para reproducir el análisis

1. Solicita acceso a los archivos a la UAO.
2. Colócalos en esta carpeta `data/`.
3. Ejecuta el notebook `notebook/UAO_Riesgo_Crediticio.ipynb`.

La semilla aleatoria y la fecha de corte están fijas en el notebook, por lo que con los mismos datos los resultados son **determinísticamente reproducibles**.
