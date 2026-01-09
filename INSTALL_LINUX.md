
# 🐧 Instalación de Clopri en Linux

Clopri es compatible con la mayoría de las distribuciones de Linux. Ofrecemos dos formatos oficiales: un paquete nativo `.deb` (recomendado para Ubuntu/Debian) y un `.AppImage` (universal para cualquier distribución).

---

## Opción A: Ubuntu / Debian / Linux Mint (Recomendado)

El archivo `.deb` instala Clopri en tu sistema, añade el icono al menú de aplicaciones y se integra mejor con el escritorio.

[![Descargar .deb](https://i.ibb.co/7Nn3Cjdv/btn-Ubuntu.png)](https://github.com/Clopri/clopri-releases/releases/download/latest/Clopri-Setup.deb)

### 🖱️ Método 1: Instalación Gráfica (Doble Clic)
1. Descarga el archivo `.deb` usando el botón de arriba.
2. Ve a tu carpeta de descargas.
3. Haz **doble clic** sobre el archivo `Clopri-Setup.deb`.
4. Se abrirá el gestor de software (Ubuntu Software o Gdebi). Haz clic en **"Instalar"**.
5. ¡Listo! Busca "Clopri" en tu menú de aplicaciones.

### Instalar Gdebi 

```bash
# 1. Descargar la última versión de Gdebi en ubuntu

# Actualizar
sudo apt-get update

#Instalar Gdebi
sudo apt-get install gdebi
```


### 💻 Método 2: Instalación por Terminal
Si prefieres la línea de comandos, abre tu terminal y ejecuta:

```bash
# 1. Descargar la última versión
wget https://github.com/Clopri/clopri-releases/releases/download/latest/Clopri-Setup.deb
# 2. Instalar el paquete
sudo dpkg -i Clopri-Setup.deb

# 3. (Opcional) Si hay errores de dependencias, ejecuta esto para corregirlo:
sudo apt-get install -f

```

---

## Opción B: AppImage (Universal / Portable)


[![Descargar .AppImage](https://i.ibb.co/kgwTjjsp/btn-Linux.png)](https://github.com/Clopri/clopri-releases/releases/download/latest/Clopri-Setup.AppImage)


El formato AppImage funciona en casi todas las distribuciones (Fedora, Arch, CentOS, Ubuntu, etc.) y no requiere instalación. Es como un archivo portable.

### ⚙️ Cómo ejecutar el AppImage

Por seguridad, Linux bloquea la ejecución de archivos descargados por defecto. Debes dar permiso una sola vez.

#### Método Visual:

1. Descarga el archivo `.AppImage`.
2. Haz **clic derecho** sobre el archivo y selecciona **Propiedades**.
3. Ve a la pestaña **Permisos**.
4. Marca la casilla: **"Permitir ejecutar el archivo como un programa"** (o "Allow executing file as program").
5. Cierra la ventana y haz **doble clic** para abrir Clopri.

#### Método Terminal:

```bash
# 1. Dar permisos de ejecución
chmod +x Clopri-Setup.AppImage

# 2. Ejecutar
./Clopri-Setup.AppImage

```

---

## 🔧 Solución de Problemas Comunes

### 1. El AppImage no abre (Ubuntu 22.04 / 24.04 o superior)

**Error:** Haces doble clic en el AppImage y no pasa nada.
**Causa:** Las versiones nuevas de Ubuntu no traen instalada la librería `FUSE` necesaria para montar AppImages antiguos.
**Solución:** Ejecuta este comando en la terminal una sola vez:

```bash
sudo apt install libfuse2

```

Intenta abrir el AppImage nuevamente.

### 2. Error de "Sandbox"

Si tu sistema tiene configuraciones de seguridad muy estrictas (común en algunos servidores o Debian sin entorno gráfico completo), podrías necesitar ejecutar la app sin la sandbox de Chrome:

```bash
./Clopri-Setup.AppImage --no-sandbox

```

### 3. Error al instalar el .deb: "Dependency is not satisfiable"

Si al instalar el `.deb` te da un error de dependencias, suele arreglarse forzando la instalación de las librerías faltantes:

```bash
sudo apt --fix-broken install

```

##

Clopri dev Support
