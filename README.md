# OVA para Desarrollo y Testing de Aplicaciones PHP con Laravel 11.4

Esta OVA está configurada para facilitar el desarrollo y testing de aplicaciones PHP basadas en el framework Laravel 11.4 en entornos locales. La configuración está diseñada para ser usada en un entorno de desarrollo y no incluye configuraciones de VHOSTs, IPTables ni SSL para evitar complicaciones innecesarias en este contexto.

## Características de la OVA

- **Sistema Operativo:** Ubuntu 24.04 LTS
- **Servidor Web:** Apache 2.4.62
- **Lenguaje de Programación:** PHP 8.3
- **Framework:** Laravel 11.4
- **Base de Datos:** MySQL 8.3.9
- **Acceso Sesión, SSH y MySQL:**
  - **Usuario:** `devadmin`
  - **Contraseña:** `d3v4dm1n`

## Descargar, Acceso y Uso

Antes de nada, es necesario descargar la OVA, para ello haz click en el siguiente enlace:
[Desarrollo de Aplicaciones con Laravel 11.4.ova](https://mega.nz/file/5gYl3YAL#eOtvmKNIPnnFG2PBAo0esnqdcy61jY46d36YcD2wBbk)

Para poder hacer uso de esta OVA, es necesario importarla en un Virtualbox o VMware, y configurar la interfaz de red como NAT o otra de las opciones. Una vez se configure y arranque la VM, se deberá acceder con las credenciales de Sesión, y, para obtener la dirección IP de la máquina, ejecutar el comando

```bash
ip a
```
**ESTE DATO ES IMPORTANTE PARA LA CONFIGURACIÓN DEL FRAMEWORK**

### SSH

Para acceder a la máquina virtual a través de SSH, utiliza las siguientes credenciales:

- **Usuario:** `devadmin`
- **Contraseña:** `d3v4dm1n`

```bash
ssh devadmin@<IP-de-la-OVA>
```

### MySQL

Para acceder a MySQL:

```bash
mysql -u devadmin -p
```

### Configuración del Framework
Dada la necesidad de establecer un parámetro denominado `APP_URL` para el correcto funcionamiento del framework, y a que esta OVA es de libre distribución y adaptable a cualquier entorno, se debe obtener la IP de la máquina (ip local) para agregar esta en el fichero `/var/www/html/.env` como valor del parámetro base_url de la siguiente forma:
```
APP_URL=http://<IP-de-la-OVA>/
```

### Entorno de trabajo
- El entorno de trabajo Laravel se ubica en el directorio `/var/www/html` y el DocumentRoot es `/var/www/html/public`.
- El los ficheros de SGBD (phpmyadmin) se encuentran en `/var/www/html/public/sql`
- Los accesos a través de Navegador Web son:
  1 Aplicación Laravel: http://<IP-de-la-OVA>/
  2 SGBD: http://<IP-de-la-OVA>/sql/

### Apache

La configuración de Apache está preparada para servir el proyecto desde el directorio `/var/www/html/public`. No es necesario modificar configuraciones de VHOSTs para el entorno de desarrollo.

### PHP

La OVA incluye PHP 8.3 con las extensiones necesarias para ejecutar CodeIgniter y otras aplicaciones web comunes. Si necesitas instalar extensiones adicionales, puedes hacerlo usando `apt`.

```bash
sudo apt install php-<extension>
```

## Notas Adicionales

- Esta OVA está configurada para entornos locales y no se recomienda su uso en producción.
- Para cualquier problema o pregunta, contacta conmigo.

## Licencia

Esta OVA se proporciona tal como está, sin garantías de ningún tipo. Usa bajo tu propia responsabilidad.
