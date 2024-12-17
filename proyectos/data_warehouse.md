# Data warehouse

Un data warehouse (almacén de datos) es un sistema de información diseñado para facilitar el análisis y la toma de decisiones en una organización.

Las principales características de un data warehouse son:

1. Orientado a temas: Está diseñado para analizar los principales temas o áreas de interés de la organización. En nuestro caso: registros, pronósticos, parámetros, metadata, entre otros.

2. Integrado: Integra datos de diversas fuentes operacionales, limpiándolos y consolidándolos en una única base de datos.

3. Histórico: Almacena datos históricos, permitiendo analizar la evolución de los indicadores a lo largo del tiempo.

4. No volátil: Los datos del data warehouse no se modifican, solo se agregan nuevos registros a medida que pasa el tiempo.

En resumen, un data warehouse es un repositorio central de datos integrados y depurados, diseñado para facilitar el análisis y la toma de decisiones estratégicas en una organización.

## Datos a agregar

| Nombre | Descripción | Agregado |
| ------ | ----------- | -------- |
| `registros.puntos.convencionales` | Son los datos de registro de las estaciones convencionales. Esto incluye registros, metadata, vacaciones y errores. | :heavy_check_mark: |
| `registros.puntos.icc` | Son los datos de registro de las estaciones icc. Esto incluye registros, metadata, vacaciones y errores. | :heavy_check_mark: |
| `registros.puntos.alfa` | Son los datos de registro de las estaciones alfa. Esto incluye registros, metadata, vacaciones y errores. | :heavy_check_mark: |
| `registros.puntos.davis` | Son los datos de registro de las estaciones automáticas davis. Esto incluye registros y metadata. | :x: |
| `registros.puntos.uicn` | Son los datos de registro de las estaciones de UICN. Esto incluye registros y metadata. | :x: |
| `registros.raster.goes` | Son los datos de registro satelital en raster de las distintas bandas del [GOES](https://www.star.nesdis.noaa.gov/GOES/sector.php?sat=G16&sector=cam). Esto incluye registros y metadata. | :x: |
| `registros.raster.???` | Otros posibles registros satelitales en formato raster. | :grey_question: |
| `registros.puntos.???` | Otros posibles registros de estaciones. | :grey_question: |
| `pronosticos.raster.wrf` | Son los raster de salida de ejecuciones del modelo WRF. Además se incluyen los valores de parámetros de entrada de ejecución | :x: |
| `pronosticos.raster.nextgen` | Son los raster de salida de ejecuciones de NextGen. Además se incluyen los valores de parámetros de entrada de ejecución | :x: |
| `pronosticos.raster.source` | [Modelos de pronóstico](http://iridl.ldeo.columbia.edu/SOURCES/). Son varias entradas para cada `source`, estos son obtenidos de las fuentes oficiales de los modelos que se utilizan en la ejecución de NextGen. Actualmente están almancenados en la librería de datos del IRI, pero esta podría dejar de dar soporte, por lo que deben ser trasladados de manera local progresivamente. | :x: |
| `pronosticos.puntos.???` | Otros posibles datos de modelos y pronósticos puntuales (por estación por ejemplo). | :grey_question: |
| `pronosticos.raster.???` | Otros posibles datos de modelos y pronósticos en formato raster | :grey_question: |
| `pronosticos.shapes.???` | Otros posibles datos de modelos y pronósticos en formato shapefile | :grey_question: |
| `herramientas.shapes.???` | Shapefiles para realizar mapas | :grey_question: |
| `index` | Índice explicando los contenidos de las tablas y views de la base de datos. |

Todas las tablas y categorías pueden tener asociadas views para distintos usuarios y aplicaciones. La descripción de estas views también debe estar contenida en el índice (`index`). También pueden haber vistas del mismo índice, asociadas a tipos de usuario.

## Uso de [PostGIS](https://postgis.net/)

PostGIS es una extensión geoespacial para el sistema de gestión de bases de datos PostgreSQL. Proporciona soporte para objetos geográficos, permitiendo que PostgreSQL funcione como una base de datos espacial.

Algunas de las principales características de PostGIS son:

1. Tipos de datos geométricos: PostGIS agrega tipos de datos geométricos como puntos, líneas, polígonos, etc. a PostgreSQL, lo que permite almacenar y manipular datos espaciales.

2. Funciones espaciales: PostGIS proporciona una amplia gama de funciones espaciales para realizar operaciones como cálculo de áreas, distancias, intersecciones, etc. sobre los datos geométricos.

3. Indexación espacial: PostGIS utiliza índices espaciales, como el índice R-Tree, para mejorar el rendimiento de las consultas espaciales.

4. Compatibilidad con estándares: PostGIS es compatible con los estándares de la industria, como Simple Features for SQL (SFSQL) y Open Geospatial Consortium (OGC).

5. Integración con SIG: PostGIS se integra bien con software de Sistemas de Información Geográfica (SIG) como QGIS, ArcGIS, etc. permitiendo el almacenamiento y análisis de datos geoespaciales.

En resumen, PostGIS convierte a PostgreSQL en una potente base de datos espacial, ampliando sus capacidades para el manejo y análisis de datos geográficos y geoespaciales.

## Librería de datos de IRI

La Biblioteca de Datos IRI es un poderoso y de libre acceso repositorio de datos en línea y herramienta de análisis que permite a un usuario ver, analizar y descargar cientos de terabytes de datos relacionados con el clima a través de un navegador web estándar.

Es una herramienta poderosa que ofrece las siguientes capacidades sin costo para el usuario:

- Acceder a cualquier número de conjuntos de datos;
- Crear análisis de datos que van desde promedios simples hasta análisis EOF más avanzados utilizando el Lenguaje de Análisis de Datos Ingrid;
- Monitorear las condiciones climáticas actuales con mapas y análisis en la Sala de Mapas;
- Crear representaciones visuales de los datos, incluidas animaciones;
- Descargar datos en una variedad de formatos de uso común, incluidos formatos compatibles con SIG.

La librería está disponible en: [http://iridl.ldeo.columbia.edu/](http://iridl.ldeo.columbia.edu/)
