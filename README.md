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
|gtMapTools| - | Terminado. Mantenimiento y mejoras. | Dar mantenimiento a la biblioteca gtMapTools que permite realizar mapas de manera automatizada. Actualizar con mejoras que ayuden al flujo de trabajo y al uso generalizado de la misma.| [gtMapTools](https://github.com/Aplicaciones-Climaticas-INSIVUMEH/gtMapTools)|
|imet| - | En progreso | Desarrollar funciones que incorporen un uso más amigable con el usuario (programadores) para la consulta de datos, creación rápida de mapas y tablas, y conexión con la nube de Google.| [imet](https://github.com/Ciencia-de-Datos-Meteorologia/imet) |
|Administración de servidores| - | Terminado en el equipo actual, en espera de nuevos servidores. Mantenimiento y nuevas incorporaciones. | Instalar los sistemas operativos en los servidores y habilitar los usuarios y máquinas virtuales requeridas por las secciones.| [sisadmin](proyectos/sisadmin.md) |
|Clases y plantillas de LaTeX | - | Terminado. Mantenimiento y nuevas incorporaciones. | Dar mantenimiento, actualizaciones y fabricar nuevas plantillas y clases de LaTeX para el uso del Departamento.|[LaTeX_Templates_project](https://github.com/orgs/Ciencia-de-Datos-Meteorologia/projects/1/)|



## Plan 2025 - 2026

- Continuar desarrollando la base de datos "Data Warehouse", realizar pruebas e implementar su uso progresivamente, sustituyendo la actual base de datos de Climatología, además de permitir el alojamiento de los pronósticos realizados por Aplicaciones Climáticas y Cambio climático. 
- Progresivamente añadir a la Data Warehouse, fuentes de modelos climáticos utilizados actualmente para el pronóstico NextGen. Ya que por el momento se depende de la [librería de datos de IRI](https://iridl.ldeo.columbia.edu).
- Verificar la instalación del Data Center, instalar los sistemas operativos en los servidores y habilitar los usuarios y máquinas virtuales requeridas por las secciones.
- Montar servicios ([Overleaf](https://github.com/overleaf/overleaf) por ejemplo) de uso del Departamento en máquinas virtuales creadas en los servidores del Data Center.
- Desarrollar bibliotecas de funciones recurrentes, como el desarrollo de mapas, tablas, gráficas; la sincronización con la nube de google; consultas a la base de datos; entre otros.
- Gestionar la asignación de IPs estáticas a las computadoras del Departamento, administrar la redirección de puertos y los accesos seguros por SSH con parejas de llaves publico-privadas.
- Desarrollar y actualizar plantillas de LaTeX para el uso del Departamento.

## Otras ideas

- Releases
