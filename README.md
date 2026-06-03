# Proyecto final – Bases de Datos Distribuidas ENOE/ENOEN

## Resumen del proyecto
Este proyecto consistió en diseñar una base de datos centralizada a partir de la Encuesta Nacional de Ocupación y Empleo (ENOE/ENOEN), normalizarla a tercera forma normal y construir posteriormente un esquema distribuido mediante fragmentación horizontal por periodo.

El trabajo se realizó con información comprendida entre **2020 3T y 2025 4T**. Se excluyó **2020 1T** debido a que su estructura presentaba diferencias importantes respecto al resto del histórico, lo que dificultaba una integración homogénea.

El modelo final quedó conformado por las tablas:

- `periodo`
- `vivienda`
- `hogar`
- `persona`

Posteriormente se generaron dos fragmentos distribuidos:

- **Fragmento 1:** 2020–2022
- **Fragmento 2:** 2023–2025

Además, para facilitar la revisión, el proyecto se migró de **SQLite a PostgreSQL**, conservando la misma estructura y validando que los conteos y periodos coincidieran correctamente.

## Contenido del repositorio

### Trabajo escrito
Documento principal del proyecto con desarrollo metodológico, diseño centralizado, fragmentación, consultas, validaciones y migración a PostgreSQL.

- [Descargar trabajo escrito](docs/Proyecto_Final_ENOE_Distribuidas_con_portada_migracion_postgres.docx)

### Scripts
Documento anexo con el diagrama E/R y los scripts utilizados durante el desarrollo del proyecto, incluyendo análisis de estructura, creación de base, carga histórica, fragmentación, consultas, validación y exportación para migración.

- [Descargar documento de scripts](docs/Scripts_y_Diagrama_ER_ENOE_con_portada_actualizado_bonito.docx)

### Respaldos de bases de datos
Respaldos finales del proyecto en PostgreSQL:

- [Descargar base centralizada](respaldos/enoe_central.backup)
- [Descargar fragmento 1](respaldos/enoe_frag_1.backup)
- [Descargar fragmento 2](respaldos/enoe_frag_2.backup)

## Herramientas utilizadas
- SQLite
- PostgreSQL
- pgAdmin
- Python
- pandas

## Estructura lógica del proyecto
El esquema centralizado se construyó con una relación jerárquica entre tablas:

- Un **periodo** contiene múltiples **viviendas**
- Una **vivienda** puede contener varios **hogares**
- Un **hogar** puede contener múltiples **personas**

## Notas finales
El desarrollo original se realizó en SQLite debido a restricciones de instalación en la computadora de trabajo. Posteriormente, se efectuó una migración complementaria a PostgreSQL para facilitar la revisión de las bases y la entrega de respaldos en un gestor ampliamente utilizado.
