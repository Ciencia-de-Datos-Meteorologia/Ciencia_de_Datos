# Administración de servidores

La administración de servidores se divide en algunas categorías principales:

## Configuración inicial

Se debe dar seguimiento a la colocación física del hardware utilizado, con las especificaciones necesarias para su funcionamiento (conexión de red, UPS, refrigeración, acceso a puertos, entre otros).

Se debe instalar un sistema operativo para el uso del servidor, los procedimientos utilizados para realizar estas configuraciones se encuentran en el repositorio de [notas](https://github.com/Ciencia-de-Datos-Meteorologia/notes/).

También se deben crear los usuarios con los permisos adecuados para que las personas que requieran utilizar el hardware, tengan acceso a este. Dependiendo de la administración del equipo, se deben crear máquinas virtuales para acceso delimitado al equipo.

Se debe instalar un firewall como sistema de seguridad. Idealmente se trabajará con sistema operativo Debian y Debian Firewall.

Se creará un `bridge` como sistema de manejo de puertos de red físicos y virtuales.

## Mantenimiento

Por seguridad, los servidores se deben mantener actualizados. Además se deben revisar los accesos, permisos, redireccionamientos, tráfico y cualquier otro tema relacionado con la seguridad de los servidores. Se deberá actualizar el firewall de acuerdo a las necesidades, así como crear nuevos usuarios o máquinas virtuales de ser necesario. 

## Instalación de programas

Distintos usuarios harán uso de distintos programas, de ser necesario, se puede otorgar permisos de instalación de repositorios oficiales a algunos usuarios, pero si estos solo harán uso de programas específicos, entonces estos programas pueden ser instalados directamente durante el proceso de configuración del usuario que los solicite.
