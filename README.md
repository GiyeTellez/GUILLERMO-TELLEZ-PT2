# GUILLERMO-TELLEZ-PT2

En este repositorio encontrarás una documentación a modo de manual de instalación y configuración de ownCloud en un sistema Linux.

## Estructura del repositorio

- **INSTALLATION.md**: Guía detallada de la instalación, instalación de dependencias y despliegue de ownCloud.
- **CONFIGURATION.md**: Manual de configuración de usuarios, roles, permisos y gestión de archivos en ownCloud.
- **README.md**: Introducción del proyecto y links a los manuales.

## Descripción del proyecto

El objetivo de esta práctica es:
1. Configurar un entorno de virtualización (IsardVDI) para alojar ownCloud.
2. Instalar y poner en marcha ownCloud (Apache, PHP, MySQL).
3. Crear usuarios con distintos roles (administrador, editor, visualizador) y asignar permisos.
4. Probar funcionalidades básicas: subida de archivos, creación de carpetas, organización y compartición.

# Manuales:

Manual de instalación de OWNCLOUD: <a href="INSTALLATION.md">Manual de instalación</a>
Configuración OWNCLOUD:  <a href="CONFIGURATION.md">Manual de configuración</a>

---

## Retos encontrados

- **Compatibilidad de PHP**: La versión stable de ownCloud (20240724) requiere PHP ≤7.4, por lo que fue necesario bajar desde PHP 8.0.
- **Permisos en /var/www/html**: Ajustar ownership y permisos a `www-data` para evitar errores de escritura.



