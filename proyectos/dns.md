# DNS

DNS (Domain Name System) es un sistema de nomenclatura jerárquico y distribuido que se utiliza para traducir nombres de dominio legibles por humanos a direcciones IP, que son los identificadores numéricos utilizados por los dispositivos en una red para comunicarse entre sí.

Algunas de las principales funciones del DNS son:

1. Resolución de nombres de dominio: Cuando un usuario ingresa un nombre de dominio (como www.example.com) en un navegador web, el DNS traduce ese nombre a la dirección IP correspondiente, permitiendo que el navegador pueda conectarse al servidor web correcto.

2. Enrutamiento de correo electrónico: El DNS también se utiliza para determinar la dirección IP del servidor de correo electrónico asociado con un dominio específico, lo que permite el envío y recepción de correos electrónicos.

3. Balanceo de carga: El DNS puede distribuir el tráfico entre varios servidores web o de aplicaciones, equilibrando la carga y mejorando el rendimiento y la disponibilidad.

4. Redundancia y tolerancia a fallos: El sistema DNS es descentralizado y distribuido, lo que significa que si un servidor DNS falla, otros servidores pueden asumir su función, manteniendo la disponibilidad del sistema.

En resumen, el DNS es un componente fundamental de Internet, ya que permite que los usuarios puedan acceder a sitios web y servicios en línea utilizando nombres de dominio fáciles de recordar, en lugar de tener que memorizar las direcciones IP.

## Montaje de un DNS

Los pasos para montar un DNS en un servidor Debian son los siguientes:

1. Instalar el paquete del servidor DNS:
```bash
sudo apt-get update
sudo apt-get install bind9
```

2. Editar el archivo de configuración principal de BIND:
```bash
sudo nano /etc/bind/named.conf.options
```
En este archivo, se debe configurar las siguientes opciones:
- `directory "/var/cache/bind";`: Establece el directorio donde se almacenarán los archivos de zona.
- `forwarders { 8.8.8.8; 8.8.4.4; };`: Configura los servidores DNS de Google como servidores de reenvío.
- `dnssec-validation auto;`: Habilita la validación DNSSEC.

3. Crear un archivo de zona para registrar los nombres de dominio:
```bash
sudo nano /etc/bind/db.domainnames
```
En este archivo, debes definir los registros DNS para tu dominio. Por ejemplo:
```bash
$TTL    604800
@       IN      SOA     example.com. root.example.com. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      ns1.example.com.
@       IN      A       172.20.3.61
ns1     IN      A       172.20.3.61
www     IN      A       172.20.3.61
```

4. Editar el archivo de configuración principal de BIND:
```bash
sudo nano /etc/bind/named.conf.local
```
En este archivo, se debe agregar la zona que se creó anteriormente:
```bash
zone "example.com" {
    type master;
    file "/etc/bind/db.domainnames";
};
```

5. Reiniciar el servicio BIND:
```bash
sudo systemctl restart bind9
```

Una vez completados estos pasos, el servidor DNS estará configurado y listo para ser utilizado en tu red local. Se debe configurar a los clientes para que utilicen la dirección IP del servidor DNS creado (por ejemplo, 172.20.3.61) como servidor DNS primario.

## Agregar una nueva IP

Para agregar una nueva dirección IP y asociarla a un nombre de host en tu servidor DNS, se debe modificar el archivo de zona creado. Este es un ejemplo de cómo agregar la dirección IP 172.20.3.60 con el nombre de host "Zuko":

1. Abrir el archivo de zona:
```bash
sudo nano /etc/bind/db.domainnames
```

2. Agregar la siguiente línea al final del archivo:
```bash
Zuko    IN      A       172.20.3.60
```

Quedando el archivo de zona así:

```bash
$TTL    604800
@       IN      SOA     example.com. root.example.com. (
                              3         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@       IN      NS      ns1.example.com.
@       IN      A       172.20.3.61
ns1     IN      A       172.20.3.61
www     IN      A       172.20.3.61
Zuko    IN      A       172.20.3.60
```

3. Guardar los cambios y reiniciar el servicio BIND:
```bash
sudo systemctl restart bind9
```

Ahora, cualquier dispositivo en la red local que consulte el nombre de host "Zuko" será redirigido a la dirección IP 172.20.3.60.

Se debe de **incrementar el número de serie en el registro SOA** cada vez que se realicen cambios, para que los clientes puedan detectar las actualizaciones.

## Descripción del archivo de zona
1. **$TTL 604800**: Este es el valor de Time to Live (TTL) predeterminado para todos los registros en esta zona. En este caso, es de 604800 segundos (7 días).

2. **@**: Este símbolo representa el nombre de dominio de la zona, en este caso, "example.com".

3. **IN**: Indica que este es un registro de Internet (Internet class).

4. **SOA**: Este es un registro de inicio de autoridad (Start of Authority), que contiene información importante sobre la zona, como:
   - **example.com.**: El nombre de dominio de la zona.
   - **root.example.com.**: El nombre del administrador de la zona.
   - **2**: El número de serie, que se incrementa cada vez que se realizan cambios en la zona.
   - **604800**: El tiempo de refresco, en segundos, para que los servidores secundarios vuelvan a cargar la zona.
   - **86400**: El tiempo de reintento, en segundos, para que los servidores secundarios vuelvan a intentar la transferencia de zona si falla.
   - **2419200**: El tiempo de caducidad, en segundos, después del cual los servidores secundarios deben considerar que la zona es obsoleta.
   - **604800**: El tiempo de vida negativo en caché, en segundos, para los registros que no se encuentran.

5. **NS**: Este es un registro de servidor de nombres (Name Server), que indica que "ns1.example.com." es el servidor de nombres autoritativo para la zona "example.com".

6. **A**: Este es un registro de dirección (Address), que mapea un nombre de host a una dirección IP. En este caso:
   - **@** (el dominio de la zona) se asigna a la IP 192.168.1.100.
   - **ns1** se asigna a la IP 192.168.1.100.
   - **www** se asigna a la IP 192.168.1.100.
   - **Zuko** se asigna a la IP 172.20.3.60.

Estas columnas definen la estructura y el contenido de la zona DNS, permitiendo que los servidores DNS resuelvan correctamente los nombres de dominio a sus direcciones IP correspondientes.
