# Cómo instalar Git en Windows



\
ACTUALIZADO 26 DE OCTUBRE DE 2022, 10:29 A. M. EST | 1 MINUTO DE LECTURA

![El logotipo de Git sobre un fondo genérico de Windows.](https://www.howtogeek.com/wp-content/uploads/2022/09/git.png?width=1198\&trim=1,1\&bg-color=000\&pad=1,1)

Descargue el instalador de Git del sitio web oficial de Git en git-scm.com y luego ejecute el ejecutable. También puede instalar Git ejecutando "winget install --id Git.Git -e --source winget" en PowerShell.

Git es una herramienta esencial si vas a programar. Le permite administrar convenientemente diferentes versiones de código dentro de un repositorio (repo). Git también es la forma más común de acceder a GitHub, uno de los repositorios de código más grandes del mundo. Aquí hay algunas formas de instalar Git en Windows.

### Descargar el ejecutable de Windows

La forma más fácil de obtener Git es descargar el ejecutable del  [sitio web de Git](https://git-scm.com/download/win) .

Haga clic en "Configuración de Git para Windows de 64 bits" para iniciar la [descarga](https://www.howtogeek.com/771533/where-are-my-downloads-on-windows/) y luego espere un momento: la descarga es de solo unos 50 megabytes, por lo que no debería llevar mucho tiempo.

![](https://www.howtogeek.com/wp-content/uploads/2022/09/pic-1-1.png?trim=1,1\&bg-color=000\&pad=1,1)

**RELACIONADO:** [_**¿Dónde están mis descargas en Windows?**_](https://www.howtogeek.com/771533/where-are-my-downloads-on-windows/)

Haga doble clic en el ejecutable que acaba de [descargar](https://www.howtogeek.com/771533/where-are-my-downloads-on-windows/) , luego haga clic en "Siguiente" para pasar por las indicaciones de instalación. Hay un montón de opciones durante el proceso de instalación; no se preocupe demasiado por la mayoría de ellas. Las opciones predeterminadas estarán bien, pero hay dos que debe tener en cuenta.

El primero es el editor de texto que usará Git. La selección predeterminada es Vim. Vim es omnipresente y un sello distintivo de las interfaces de línea de comandos en todas partes, pero aprender a usar sus comandos idiosincrásicos puede ser desalentador. Probablemente debería elegir otra cosa en su lugar, como Visual Studio Code, Sublime, NotePad ++ o cualquier otro [editor de texto sin formato](https://www.howtogeek.com/795509/why-you-need-a-plain-text-editor/) que desee.

Simplemente haga clic en el menú desplegable y luego seleccione el nuevo programa de la lista.

> **Sugerencia:** Pruebe Visual Studio Code si no sabe cuál elegir.

![](https://www.howtogeek.com/wp-content/uploads/2022/09/pic-2-1.png?trim=1,1\&bg-color=000\&pad=1,1)

La segunda es la forma en que Git se integra en el [PATH](https://www.howtogeek.com/118594/how-to-edit-your-system-path-for-easy-command-line-access/) de su PC . Asegúrese de que esté seleccionado "Git desde la línea de comandos y también desde software de terceros".

**RELACIONADO:** [_**Cómo editar la RUTA de su sistema para acceder fácilmente a la línea de comandos en Windows**_](https://www.howtogeek.com/118594/how-to-edit-your-system-path-for-easy-command-line-access/)

![Asegúrese de seleccionar la opción que agrega Git a su sistema PATH.](https://www.howtogeek.com/wp-content/uploads/2022/09/pic-3.png?trim=1,1\&bg-color=000\&pad=1,1)

Haga clic en las opciones restantes y espere a que todo termine de descargarse. El tiempo requerido para descargar todo variará según lo que elija instalar. La selección predeterminada da como resultado una descarga de aproximadamente 270 megabytes.

### Usa Winget para descargar Git

También puedes usar [Winget](https://www.howtogeek.com/674470/how-to-use-windows-10s-package-manager-winget/) para descargar Git si eres fanático de las interfaces de línea de comandos.

**RELACIONADO:** [_**Cómo usar el Administrador de paquetes de Windows 10, "winget"**_](https://www.howtogeek.com/674470/how-to-use-windows-10s-package-manager-winget/)

Abra PowerShell o Windows Terminal con una pestaña de PowerShell y luego pegue o escriba:

```
winget install --id Git.Git -e --source winget
```

Verá que aparecen algunas barras de descarga en la ventana de la Terminal mientras Winget obtiene todo lo que necesita.

![Winget obteniendo archivos de GitHub.](https://www.howtogeek.com/wp-content/uploads/2022/09/pic-4.png?trim=1,1\&bg-color=000\&pad=1,1)

Aparecerá una ventana de instalación normal de Windows como parte final del proceso de instalación.

![La parte final del proceso de instalación.](https://www.howtogeek.com/wp-content/uploads/2022/09/pic-5.png?trim=1,1\&bg-color=000\&pad=1,1)

Estás listo para irte después de que esa ventana se cierre. Encontrará que Git se ha agregado a la RUTA. Cualquier programa que requiera su instalación, como [Stable Diffusion](https://www.howtogeek.com/830179/how-to-run-stable-diffusion-on-your-pc-to-generate-ai-images/) , ahora funcionará correctamente.
