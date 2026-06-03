# Proyecto final – Bases de Datos Distribuidas ENOE/ENOEN

> Diseño centralizado, fragmentación horizontal y migración complementaria de SQLite a PostgreSQL.

---

## Introducción
Este proyecto se desarrolló a partir de la Encuesta Nacional de Ocupación y Empleo (ENOE/ENOEN) con el objetivo de construir una base de datos centralizada, normalizarla a tercera forma normal y posteriormente diseñar un esquema distribuido mediante fragmentación horizontal por periodo.

El trabajo se realizó con información comprendida entre **2020 3T y 2025 4T**, excluyendo **2020 1T** debido a que su estructura presentaba diferencias importantes respecto al resto del histórico, lo que dificultaba la integración homogénea de variables. A partir del análisis de las familias de datos disponibles, se definió un modelo estable conformado por las tablas **periodo**, **vivienda**, **hogar** y **persona**.

Posteriormente, la base centralizada se fragmentó en dos partes: un primer fragmento para los años **2020 a 2022** y un segundo fragmento para los años **2023 a 2025**. Con ello se logró construir un esquema distribuido funcional y validar que los resultados obtenidos coincidieran con los de la base centralizada.

Debido a restricciones de instalación en la computadora de trabajo, el desarrollo original del proyecto se realizó en **SQLite**. Sin embargo, para facilitar la revisión de los respaldos y la entrega final, también se llevó a cabo una **migración complementaria a PostgreSQL**, manteniendo la misma estructura lógica y verificando la correcta separación de periodos y conteos.

---

## Contenido del trabajo
El proyecto incluye:

- análisis de la estructura histórica de los archivos ENOE/ENOEN
- selección de variables homogéneas
- diseño centralizado en 3FN
- modelo entidad–relación
- creación y carga de la base centralizada
- fragmentación horizontal por periodo
- consultas centralizadas y distribuidas
- validación de la distribución
- migración de SQLite a PostgreSQL para respaldo y revisión

---

## Documentación del proyecto

### Trabajo escrito
Documento principal con la explicación completa del desarrollo del proyecto, desde el análisis inicial hasta la validación final y la migración a PostgreSQL.

- [Ver trabajo escrito en PDF](./PROYECTO%20FINAL/docs/Trabajo_escrito.pdf)

### Scripts del proyecto
Documento anexo que reúne los scripts utilizados en cada etapa del desarrollo, junto con la explicación de para qué sirve cada uno y qué se hizo en cada caso.

- [Ver documento de scripts en PDF](./PROYECTO%20FINAL/docs/Scripts.pdf)

### Carpeta general de respaldos y archivos
En esta carpeta se encuentran los respaldos del proyecto y los archivos complementarios de entrega.

- [Abrir carpeta general en Google Drive](https://drive.google.com/drive/folders/13mHeEBpRz3ZFuPVxHpjsiokDzmMQI2C4?usp=sharing)

---

## Estructura lógica del proyecto

### Base centralizada
- `enoe_central`
- Periodos: **2020 3T – 2025 4T**

### Fragmento 1
- `enoe_frag_1`
- Periodos: **2020–2022**

### Fragmento 2
- `enoe_frag_2`
- Periodos: **2023–2025**

---

## Herramientas utilizadas
- SQLite
- PostgreSQL
- pgAdmin
- Python
- pandas

---

## Nota final
El proyecto fue construido originalmente en SQLite por limitaciones del entorno de trabajo, y posteriormente se migró a PostgreSQL con fines de respaldo y de facilitación de la revisión. De esta forma, se conservó la lógica metodológica original del desarrollo y al mismo tiempo se generó una entrega más accesible para su consulta.
