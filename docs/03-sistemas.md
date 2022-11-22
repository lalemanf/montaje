---
hide:
  - footer
---

# Sistemas Operativos
<figure markdown>
  ![](media/03-sistemas.png){ width="400" }
  <figcaption></figcaption>
</figure>

En este tema veremos la diferencia que existe entre un sistema operativo y una distribución basada en un sistema operativo. Además, estudiaremos e instalaremos los diferentes sistemas y distribuciones que existen mediante la técnica de virtualización con un _software_ específico para ello.

Por otro lado, aprenderemos a manejar el sistema de particionado de discos (sobretodo en discos virtuales) y las distintas herramientas que vienen de serie en cada uno de los sistemas que vayamos a instalar.

## 📒 Vocabulario

??? INFO "Sistema anfitrión (Host)"
    Es el sistema operativo que se arranca cuando encendemos el ordenador original, el físico.

??? INFO "Sistema huésped (Guest)"
    Es el sistema operativo que se inicia a través de un _software_ de virtualización como **VirtualBox**


## 👩‍🚀 Virtualización
<figure markdown>
  ![](media/03-virtual.png){ width="200" }
  <figcaption></figcaption>
</figure>


Como ya sabemos lo que es un sistema operativo, vamos directamente a ver cómo podemos arrancar un sistema dentro de otro sistema operativo por medio de la técnica de virtualización.

La virtualización es una representación basada en software (es decir, virtual) de aplicaciones, servidores, almacenamiento y redes para reducir los gastos en la compra de equipos y aumentar la eficiencia y la agilidad.

La virtualización permite mejorar la agilidad, la flexibilidad y la escalabilidad de la infraestructura de TI, al mismo tiempo que proporciona un importante ahorro de costes. Algunas ventajas de la virtualización, como la mayor movilidad de las cargas de trabajo, el aumento del rendimiento y de la disponibilidad de los recursos o la automatización de las operaciones, simplifican la gestión de la infraestructura de TI y permiten reducir los costes de propiedad y operativos.

### 📦 Virtual Box

<figure markdown>
  ![](media/03-vbox.png){ width="250" }
  <figcaption></figcaption>
</figure>

VirtualBox es una aplicación que sirve para hacer máquinas virtuales con instalaciones de sistemas operativos. Esto quiere decir que si tienes un ordenador con Windows, GNU/Linux o incluso macOS, puedes crear una máquina virtual con cualquier otro sistema operativo para utilizarlo dentro del que estés usando.

En otras palabras, esto te va a permitir instalar otros sistemas operativos o el mismo que ya tienes dentro de tu ordenador. El primer caso te va a servir para probar las aplicaciones de otro sistema operativo para no tener que estar haciendo particiones o el proceso de instalar Linux junto a Windows.


#### 🔰 La pantalla principal

<figure markdown>
  ![](media/03-vbox-principal.png){ width="600" }
  <figcaption></figcaption>
</figure>

Esta es la pantalla principal del programa ***Oracle VirtualBox*** donde nos muestra un resumen de las máquinas virtuales que hemos instalado en nuestro sistema anfitrión (_host_).

Conforme vayamos creando nuevas máquinas irán apareciendo en el menú de la izquierda, pudiendo seleccionar una o varias y configurando cada una de ellas, así como iniciarlas.

!!! ERROR "Cuidado"
    Sólo se permite correr una máquina virtual a la vez, debido a los recursos del sistema.


#### 💽 Medios virtuales _(CTRL + D)_

Los **medios virtuales** son los archivos de almacenamiento que se encuentran en el sistema anfitrión (host) y que pueden contener sistemas operativos en formato de **imagen de disco** o instalados.

Dichos archivos tienen varias características en función de qué tipo de medio virtual es

=== "Sistema Operativo instalado"
    Este tipo de medio virtual es un archivo con extensión **.vdi** que contiene en su interior un sistema operativo (como Windows o Linux) ya instalado.

    Por lo general puede estar confeccionado de 2 maneras diferentes:

    - **Espacio reservado dinámicamente:** A través del menú de configuración podremos especificar el tamaño máximo de este archivo (por ejemplo 20GB) pero ocupará lo que ocupe el sistema operativo instalado dentro de el. Conforme se vaya ocupando, el archivo en el ordenador anfitrión (host) irá aumentando.
    
    - **Espacio fijo:** A través del menú de configuración podremos especificar el tamaño máximo de este archivo (por ejemplo 20GB) y en el ordenador anfitrión (host) el archivo ocupará 20GB siempre, independientemente de si el sistema que está instalado dentro del archivo ocupa o no 20GB.

    !!! INFO
        En el mundo real (no virtual) son los discos duros (HDD) o SSD.

=== "Imagen de disco"
    Las imágenes de disco suelen servir para instalar un sistema operativo o para arrancarlo de manera directa sin instalar nada.

    Gracias a estos discos podremos instalar cualquier distribución de Linux o Windows.

    !!!INFO
        En el mundo real (no virtual) suelen ser los CDs o DVDs de instalación.

---

<figure markdown>
  ![](media/03-medios-virtuales.png){ width="600" }
  <figcaption></figcaption>
</figure>

Para añadir un medio virtual, abriremos el **Administrador de medios virtuales** dentro de **VirtualBox**

##### 💾 Disco Duro Virtual

Si queremos añadir un nuevo disco duro virtual para posteriormente instalar un sistema dentro de el, pincharemos sobre el icono de **Crear**, crearemos un archivo VDI y le asignaremos **tamaño dinámico**.

<figure markdown>
  ![](media/03-hdd-virtual-1.png){ width="400" }
  <figcaption>Seleccionamos VDI</figcaption>
</figure>

Seguidamente, indicaremos dónde queremos guardar este archivo (nuestro disco duro virtual) le asignaremos un nombre (normalmente el mismo nombre que el sistema que vayamos a instalar) y definiremos el tamaño (entre 15GB y 20GB)

<figure markdown>
  ![](media/03-hdd-virtual-2.png){ width="400" }
  <figcaption>Ubicación, nombre y tamaño</figcaption>
</figure>

Una vez creado, aparecerá en la lista del gestor de medios virtuales de la siguiente manera

<figure markdown>
  ![](media/03-hdd-virtual-3.png){ width="400" }
  <figcaption>Discos virtuales</figcaption>
</figure>


##### 💿 Imagen de disco virtual

Para **añadir** una imagen de disco virtual (un instalador de sistema operativo) o archivo **.iso** primero de todo debemos descargar u obtener dicho archivo **iso** y después, en la pantalla de VirtualBox hay que apretar al botón de **Añadir**.

Vamos a trabajar con Linux Mint, así que descargaremos la última versión [desde este enlace](https://mirror.airenetworks.es/linuxmint/iso/stable/21/linuxmint-21-cinnamon-64bit.iso){target="_blank"} y una vez que tengamos el archivo descargado, deberemos agregarlo a la lista de discos a través del **Administrador de medios virtuales**

!!! WARNING "Ojo con ésto"
    Dentro del **Administrado de medios virtuales** debemos seleccionar la pestaña **Discos Ópticos** para poder añadir una imagen de disco.

<figure markdown>
  ![](media/03-iso-virtual.png){ width="400" }
  <figcaption>Imagen de disco virtual</figcaption>
</figure>


#### ⚙️ Configuración de la máquina _(CTRL + S)_
<figure markdown>
  ![](media/03-vbox-config.png){ width="600" }
  <figcaption>Configuración de la máquina virtual</figcaption>
</figure>

Para configurar una máquina virtual, la seleccionaremos de la lista de la izquierda y le daremos a configuración.

Para el ejemplo de clase vamos a trabajar con la siguiente configuración:

  - **Memoria RAM**: 4 GB
  - **Disco Duro Virtual**: LinuxMint.vdi
  - **Imagen de disco virtual**: linuxmint-21-cinnamon-64bit.iso
  - **Procesadores**: 4 (o 2 en caso de que no dispongamos de 4)
  - **Memoria de video**: 64MB


#### ▶️ Arrancando la máquina virtual
<figure markdown>
  ![](media/03-play.png){ width="200" }
  <figcaption></figcaption>
</figure>

Ahora que ya lo tenemos todo, tan sólo nos queda arrancar al máquina virtual y empezar a instalar el sistema operativo definiendo particiones de disco, programas y funcionalidades que se van a instalar, usuario y contraseña, localización, idioma entre otras.

Recuerda que cada instalador tiene su propio menú con diferentes opciones pero que algunas, como es el caso del particionado de discos es común a todos los sistemas operativos.

Más adelante veremos cómo particionar el disco correctamente para poder tener albergados varios sistemas operativos en un mismo archivo de almacenamiento virtual o **.VDI**


## 🧰 EJERCICIOS

1.- ❎ Instala Linux Mint creando los medios virtuales que necesites para llevarlo a cabo. Recuerda que el disco duro virtual debe ocupar entre 15GB y 20GB.

2.- ❎ Instala las ***Guest Additions*** de Virtual Box para poder tener la pantalla completa en la máquina virtual.

3.- ❎ Instala el programa **Visual Studio Code** mediante el gestor de paquetes de Linux Mint.

4.- ❎ Investiga todos las distribuciones de Linux de la siguiente lista y haz un resumen de cada una de ellas **mínimo 100 palabras** por cada distribución, añadiendo su logotipo al texto.

    - Ubuntu
    - Pop!_OS
    - Zorin OS
    - Elementary OS
    - Gentoo
    - Manjaro
    - Kali Linux
    - Arch Linux
    - Tiny Core
    - Kubuntu

5.- Elige una de las distribuciones que más te ha gustado de la lista anterior y **crea una máquina virtual** con dicho sistema. Acuérdate que como máximo tienes que crear un disco duro virtual de entre 15 y 20 gigas de espacio que vaya aumentando de manera dinámica.