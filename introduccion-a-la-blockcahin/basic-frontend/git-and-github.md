# Git & Github

## [Github](https://github.com/)

GitHub es una plataforma de desarrollo colaborativo basada en la web que permite a los programadores alojar y controlar versiones de su código. Es esencialmente un servicio de alojamiento de repositorios Git, que es un sistema de control de versiones distribuido utilizado para llevar un registro de las modificaciones en los archivos de un proyecto.

Con GitHub, los desarrolladores pueden crear repositorios para alojar su código, colaborar con otros desarrolladores en proyectos compartidos, realizar seguimiento de problemas, rastrear cambios y utilizar herramientas de integración continua (CI) para automatizar la construcción y el despliegue de su código.

Además de ser una plataforma para alojar y colaborar en proyectos de código abierto, GitHub también ofrece opciones de pago para equipos y organizaciones que deseen utilizarlo para proyectos privados. Esto permite a las empresas y organizaciones utilizar GitHub como una plataforma central para el desarrollo de software, la colaboración y el control de versiones.

## [Git](https://git-scm.com/)

Git es un sistema de control de versiones distribuido. Esto significa que, en lugar de tener una sola copia centralizada del código, cada desarrollador tiene su propia copia del repositorio, y puede trabajar en ella independientemente de otros desarrolladores.

Git permite a los desarrolladores almacenar y rastrear cambios en el código a lo largo del tiempo, lo que facilita la colaboración y la resolución de conflictos. Los desarrolladores pueden crear ramas (branches) de un proyecto para trabajar en características nuevas o arreglos de errores, y luego fusionarlas de nuevo en la rama principal (master) una vez que estén listas.

Además, Git permite a los desarrolladores revertir cambios, ver quién ha hecho cambios específicos en el código y por qué, y mantener un registro completo del historial del proyecto. Git es uno de los sistemas de control de versiones más populares y ampliamente utilizados en el mundo de la programación, y es compatible con una amplia variedad de lenguajes de programación y plataformas

Una vez que tienes un repositorio en GitHub, puedes invitar a otros colaboradores a trabajar en él, crear ramas (branches) para características y arreglos de errores, y crear solicitudes de extracción (pull requests) para fusionar cambios en la rama principal (master).

### Como se usa

Para usar Git y GitHub, primero debes crear una cuenta en Github  y descargar e instalar Git en tu computadora. Luego, puedes seguir estos pasos básicos:

1. Crea un nuevo repositorio local en tu computadora, utilizando el comando "git init" en la línea de comandos.
2. Agrega los archivos que deseas incluir en el repositorio, utilizando el comando "git add" seguido del nombre del archivo o carpeta.
3. Haz un "commit" de los cambios, utilizando el comando "git commit -m "mensaje del commit"". El mensaje del commit debe ser descriptivo y especificar los cambios realizados.
4. Conecta tu repositorio local con un repositorio remoto en GitHub, utilizando el comando "git remote add origin \[url del repositorio en GitHub]".
5. Sube (push) los cambios a GitHub, utilizando el comando "git push origin master".

### &#x20;



## Instalar Git&#x20;

En linux puedes utilizar el siguiente comando  o puede ir a la [web](https://git-scm.com/) oficial e instalarlo como desees&#x20;

```
sudo apt install git 
```

#### [Ver como instalar en windows](https://platohedro-1.gitbook.io/b.a.m/introduccion-a-la-blockcahin/basic-frontend/git-and-github/como-instalar-git-en-windows)

## Github-VsCode

Una forma muy amigable de utilizar Github es  por medio de la extensión  de Visual studio code, con la cual podremos integrar los repositorios de la nube con nuestro sistema de archivos local



<figure><img src="../../.gitbook/assets/nombredelgif.gif" alt=""><figcaption></figcaption></figure>



## Creando un repositorio&#x20;

Vamos a la web de [github](https://github.com/) y presionamos el boton de new repository, agregamos el nombre que le quremos dar al repositorio.&#x20;



<figure><img src="../../.gitbook/assets/create_repo.gif" alt=""><figcaption></figcaption></figure>

&#x20;



## Clonando un repositorio&#x20;

Presionas ctrl + shift + p para habilitar  el input



<figure><img src="../../.gitbook/assets/colne.gif" alt=""><figcaption></figcaption></figure>

## Config github

Escribe las siguentes  lineas de comando para vincular tu susario de github con Vscode

```
git config --global user.email "tucorreo@gmail.com"

git config --global user.name "tu_nombre_de_usuario"

```

<figure><img src="../../.gitbook/assets/config.gif" alt=""><figcaption></figcaption></figure>

## &#x20;Commit y Push&#x20;

Al hacer cambios en algun archivo en la columna derecha  se registran los cambios que tiene el archivo local con el que esta en la nube, para subuir los cambios te vas a la columna, depositas el comentario con el que quieres subiur el cambio y  presiona el boton de confirmación

<figure><img src="../../.gitbook/assets/push.gif" alt=""><figcaption></figcaption></figure>





