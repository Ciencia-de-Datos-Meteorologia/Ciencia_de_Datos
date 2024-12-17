# Sección de Ciencia de Datos

## Descripción general
La sección de ciencia de datos fue creada con el fin de proveer de herramientas computacionales a las secciones técnicas del Departamento de Investigación y Servicios Meteorológicos.

## Funciones de la sección
La sección de Ciencia de Datos se caracteriza por tres funciones principales:

- **Arquitectura de la Data Warehouse:** se encarga de diseñar la estructura de la base de datos "Data Warehouse". Además le da mantenimiento a la misma, y le agrega nuevas entradas y tablas que se adapten a las necesidades de las secciones que hacen uso de los datos.
- **Diseño de scripts y bibliotecas de automatización:** se encarga de dar mantenimiento a scripts y bibliotecas de automatización. Además diseña y desarrolla nuevos scripts y bibliotecas que permitan una mayor agilidad en la fabricación de productos. Trabaja de la mano con otras secciones para atender solicitudes de automatización específicas.
- **Administración de servidores:** se encarga de los procesos de administración de sistemas, dando mantenimiento a las computadoras utilizadas como servidor, y en el futuro, a los servidores de meteorología instalados en el Data Center. El mantenimiento del equipo incluye: instalación y actualización del sistema operativo, instalación de programas necesarios, administración de usuarios y accesos de uso, gestión de máquinas virtuales y asignación de recurso computacional.

## Misión de la sección
Innovar los flujos de trabajo de las secciones del Departamento de Investigación y Servicios Meteorológicos.

## Visión de la sección
Construir un Departamento técnico con los recursos que le permitan enfocar sus esfuerzos en la investigación y aplicación del conocimiento generado para el beneficio de la sociedad.

## Proyectos

| Proyecto | Otros responsables | Estatus | Descripción | Enlace |
| -------- | ------------------ | ------- | ----------- | ------ |
|Data Warehouse|Secciones: climatología, aplicaciones climáticas, cambio climático |En progreso|Diseñar la estructura de la base de datos "Data Warehouse", dar mantenimiento y agregar entradas requeridas por las secciones.|[data_warehouse](proyectos/data_warehouse.md)|
|Plan de adquisiciones de UICN | Jefatura, equipo administrativo, secciones: sensores remotos, climatología, meteorología. | En progreso | Dar seguimiento a las compras relacionadas al Data Center.| [plan_adq_UICN](/proyectos/plan_adq_UICN.md) |
|gtMapTools| Sección de aplicaciones climáticas | Terminado. Mantenimiento y mejoras. | Dar mantenimiento a la biblioteca gtMapTools que permite realizar mapas de manera automatizada. Actualizar con mejoras que ayuden al flujo de trabajo y al uso generalizado de la misma.| [gtMapTools](https://github.com/Aplicaciones-Climaticas-INSIVUMEH/gtMapTools)|
|imet| - | En progreso | Desarrollar funciones que incorporen un uso más amigable con el usuario (programadores) para la consulta de datos, creación rápida de mapas y tablas, y conexión con la nube de Google.| [imet](https://github.com/Ciencia-de-Datos-Meteorologia/imet) |
|Administración de servidores| - | Terminado en el equipo actual, en espera de nuevos servidores. Mantenimiento y nuevas incorporaciones. | Instalar los sistemas operativos en los servidores y habilitar los usuarios y máquinas virtuales requeridas por las secciones.| [sysadmin](proyectos/sysadmin.md) |
|Clases y plantillas de LaTeX | - | Terminado. Mantenimiento y nuevas incorporaciones. | Dar mantenimiento, actualizaciones y fabricar nuevas plantillas y clases de LaTeX para el uso del Departamento.|[LaTeX_Templates_project](https://github.com/orgs/Ciencia-de-Datos-Meteorologia/projects/1/)|
|Tests de funcionamiento| Practicantes | Sin iniciar | Fabricar programas de testeo utilizando [pytest](https://docs.pytest.org/en/stable/), [unittest](https://docs.python.org/3/library/unittest.html) o similar, con el fin de probar la funcionalidad y consistencia de los programas. Especialmente dirigido a consultas y almacenamiento de datos en la base de datos "Data Warehouse", ya que es importante verificar que la información guardada sea la correcta y su estructura se esté almacenando de la manera esperada. | [pytest](https://docs.pytest.org/en/stable/), [unittest](https://docs.python.org/3/library/unittest.html) |
|DNS|-| En progreso | Realizar un servidor DNS con los nombres de las computadoras del Departamento. | [dns]
(proyectos/dns.md) |


## Plan 2025 - 2026

- Continuar desarrollando la base de datos "Data Warehouse", realizar pruebas e implementar su uso progresivamente, sustituyendo la actual base de datos de Climatología, además de permitir el alojamiento de los pronósticos realizados por Aplicaciones Climáticas y Cambio climático. 
- Progresivamente añadir a la Data Warehouse, fuentes de modelos climáticos utilizados actualmente para el pronóstico NextGen. Ya que por el momento se depende de la [librería de datos de IRI](https://iridl.ldeo.columbia.edu).
- Verificar la instalación del Data Center, instalar los sistemas operativos en los servidores y habilitar los usuarios y máquinas virtuales requeridas por las secciones.
- Montar servicios ([Overleaf](https://github.com/overleaf/overleaf) por ejemplo) de uso del Departamento en máquinas virtuales creadas en los servidores del Data Center.
- Desarrollar bibliotecas de funciones recurrentes, como el desarrollo de mapas, tablas, gráficas; la sincronización con la nube de google; consultas a la base de datos; entre otros.
- Gestionar la asignación de IPs estáticas a las computadoras del Departamento, administrar la redirección de puertos y los accesos seguros por SSH con parejas de llaves publico-privadas.
- Desarrollar y actualizar plantillas de LaTeX para el uso del Departamento.

## Otras ideas

- **Releases:** Trabajar los proyectos con número de versión y nombre (vMAJOR.MINOR.BUGFIX ColorFruit), donde el nombre cambie cada vez que se realice un cambio de versión mayor en el producto. 
- **Uso de Machine Learning para establecer parametros de modelación dinámica:** Una vez establecida la base de datos, se puede hacer uso de Machine Learning para analizar los conjuntos de parámetros de entrada, las salidas de pronóstico (WRF,RegCM, entre otros), y los valores de registro, para entrenar modelos que ayuden a establecer los valores de configuración de parámetros de entrada. Por ejemplo, un aprendizaje reforzado que busque cambiar los valores de los parámetros de entrada, ejecute el modelo dinámico (WRF por ejemplo) con estos parámetros, y después compare la salida con los registros, y repita el procedimiento hasta ir aprendiendo como corregir los valores en los parámetros de entrada.
- **Uso de Machine Learning para post-procesamiento de modelos:** Utilizar las salidas de los modelos en retrospectiva, y los valores de los registros, para entrenar modelos de ML que puedan definir ajustes estadísticos a las salidas del modelo, mejorando la predictibilidad.
- **Post-procesamiento de registros:** Utilizar modelos para mejorar los registros.
