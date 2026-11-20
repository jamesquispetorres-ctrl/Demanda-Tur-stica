# Demanda turística en Perú y planificación de capacidad aérea

Proyecto final de Inteligencia de Negocios en Power BI. Un dashboard interactivo de 4 páginas que usa las visitas mensuales a sitios turísticos del Perú (MINCETUR, enero 2019 a junio 2026) como indicador de demanda para apoyar decisiones de capacidad aérea de una aerolínea simulada.

> **Aviso de simulación.** LATAM Airlines Perú se usa solo como escenario académico. El proyecto no usa datos internos de la empresa, no la representa y no ha sido revisado por ella. Las cifras públicas de la empresa que aparecen en el informe se citan con su fuente.

## Problema

La capacidad aérea hacia destinos turísticos (asientos y frecuencias) depende de una demanda muy estacional, concentrada en pocos destinos y capaz de caer de golpe, como ocurrió con la pandemia. Programar de menos pierde pasajeros y programar de más vuela con asientos vacíos. El proyecto construye la vista integrada de demanda que ese análisis necesita.

## Dashboard

- **Dashboard interactivo:** [Ver en Power BI](PEGAR-AQUÍ-EL-ENLACE-PÚBLICO)
- **Informe completo (PDF):** [Informe BI Demanda turística en Perú y planificación de capacidad aérea.pdf](<Informe BI Demanda turística en Perú y planificación de capacidad aérea.pdf>)

| Página | Pregunta de negocio |
|---|---|
| 1. Resumen general | ¿Cuánta demanda turística hay y qué se espera en 12 meses? |
| 2. Destinos | ¿Dónde se concentran las visitas? |
| 3. Estacionalidad y mix | ¿Cuándo sube y baja la demanda, y qué proporción es extranjera? |
| 4. Pandemia y recuperación | ¿Cuánto cayó la demanda y cuánto se recuperó? |

![Página 1: Resumen general](Imagenes/1.jpg)
![Página 2: Destinos](Imagenes/2.jpeg)
![Página 3: Estacionalidad y mix](Imagenes/3.jpeg)
![Página 4: Pandemia y recuperación](Imagenes/4.jpeg)

## Hallazgos principales

- **Concentración:** Cusco reúne cerca de la mitad de las visitas (55,4 de 114 millones), seguido de Lima e Ica.
- **Estacionalidad:** julio y agosto son los meses más altos y marzo el más bajo (sin contar la pandemia).
- **Pandemia y recuperación:** de 20,9 millones de visitas en 2019 a 4,9 millones en 2020; en 2025 la demanda llegó al 98,6 % del nivel de 2019.
- **Mix de visitantes:** el 37,59 % de las visitas con detalle son de extranjeros.

## Herramientas y técnicas

- **Power BI Desktop y Power Query (M):** ETL del archivo Excel, limpieza de texto, eliminación de duplicados y tratamiento de las filas TOTAL para evitar doble conteo.
- **Modelo en estrella:** una tabla de hechos y dos dimensiones (`dim_fecha`, `dim_sitio`) con relaciones 1:*.
- **DAX:** medidas como `% Extranjeros`, `Promedio mensual` y `Recuperación 2025 vs 2019`.
- **Análisis:** gráfico de cajas para tratar la pandemia como anomalía y previsión a 12 meses con estacionalidad.
- **Storytelling:** un mensaje por página, filtros y segmentaciones interactivas.

## Datos

Visitantes a sitios turísticos del Perú, Ministerio de Comercio Exterior y Turismo (MINCETUR), publicado en la Plataforma Nacional de Datos Abiertos:
https://www.datosabiertos.gob.pe/dataset/visitantes-sitios-tur%C3%ADsticos-del-per%C3%BA-ministerio-de-comercio-exterior-y-turismo-mincetur

Fecha de consulta: PEGAR-AQUÍ-LA-FECHA

El repositorio incluye una copia del archivo usado (`Visitantes_sitios_turisticos.xlsx`); la versión más reciente se descarga desde el enlace anterior.

## Limitaciones

- Las visitas a sitios turísticos son un indicador indirecto de la demanda aérea; el proyecto no usa pasajeros, tarifas ni ocupación.
- La previsión se entrenó con una serie que incluye la pandemia, por lo que se presenta solo como referencia.
- Los periodos de prepandemia, pandemia y recuperación son un supuesto del proyecto.
- No se comprobó en todo el archivo que TOTAL sea igual a NACIONAL más EXTRANJERO.

## Estructura del repositorio

```
Proyect_BI_LATAM/
├── README.txt
├── BI_LATAM.pbix
├── Informe BI Demanda turística en Perú y planificación de capacidad aérea.pdf
├── Visitantes_sitios_turisticos.xlsx
└── Imagenes/
    ├── 1.jpg      (Página 1: Resumen general)
    ├── 2.jpeg     (Página 2: Destinos)
    ├── 3.jpeg     (Página 3: Estacionalidad y mix)
    └── 4.jpeg     (Página 4: Pandemia y recuperación)
```

## Autor

James Brayan Quispe Torres. Estudiante de Ingeniería de Sistemas e Informática, UTP (Trujillo).
