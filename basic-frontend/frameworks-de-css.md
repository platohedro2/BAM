# Frameworks de CSS

Lo primero que tenemos que hacer es desplegar Tailwind CSS, hay muchas formas de usar este genial Framework. Puedes instalarlo como un paquete NPM en React JS, Vue JS, Angular, etc. Asimismo puedes instalarlo en frameworks y tecnologías como Next.js, Laravel, Vite, Nuxt.js, Gatsby, entre otros.

Para este tutorial usaré HTML puro, es decir, no usaré React JS, Vue JS o Angular. En otros tutoriales los usaremos, pero recuerda que si quieres usar Tailwind en otros entornos como los mencionados anteriormente, puedes revisar su [documentación oficial](https://tailwindcss.com/docs/installation/framework-guides), en donde te enseñan los pasos adecuados.

El proyecto va tener 4 páginas web, las cuales son Home, Nosotros, Servicios y Contacto. Comenzaremos

### Desplegando Tailwind CSS 3

Ya que trabajaré con HTML puro en ste tutorial, entonces usaré la CDN de Tailwind CSS, para ello instancio su url dentro de las etiquetas **\<head>\</head>**, por ejemplo:

```
 <!doctype html>
 <html> 
  <head>    
  <meta charset="utf-8">     
  <title>Home - Mi Proyecto</title>   
   <meta name="viewport" content="width=device-width, initial-scale=1.0">    
    <!-- CDN de Tailwind CSS -->    <script src="https://cdn.tailwindcss.com"></script>     
     <!-- Hoja de estilos Personalizada --> <link rel="stylesheet" href="assets/css/estilos.css">   
     </head> 
       <body>     
       <!-- Acá va el contenido de la página -->  
        </body>
        </html> 
```

Con ello ya tenemos Tailwind CSS, puedes ver que adicionalmente llamo a un archivo llamado **estilos.css**, este archivo lo he creado manualmente para escribir allí mis propios estilos CSS.

### Estructura del Proyecto

El sitio web va tener para comenzar la siguiente estructura:

| <p> /web-tailwindcss-3  </p><p></p><p>├── /assets      </p><p>         ├── css          // ... estilos CSS ...      </p><p>         ├── img          // ... imágenes ...  </p><p>├── index.html  </p><p>├── // ... Otros archivos HTML ... </p> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                                                                                                                                 |

Poco a poco esta estructura irá creciendo, conforme necesitemos implementar algunos elementos más.  Ahora pasaré a crear la primera página del sitio web.

### Página Home

Para esta página creo un archivo HTML en el directorio principal del proyecto, le pongo el nombre **index.html** ya que será el archivo para la página principal.

| <p> /web-tailwindcss-3  </p><p>├── /assets  </p><p>├── index.html // Creo y Abro este Archivo </p> |
| -------------------------------------------------------------------------------------------------- |

Abro el archivo **index.html** y empiezo creando el menú de navegación, el cual se verá en todas las páginas del sitio web, por cierto el footer también se verá en todas las páginas del sitio web y en esta primera parte del tutorial los dejaremos creados y listos para usarlos en las demás páginas.

#### Menú

Este menú va tener el logo del proyecto al lado izquierdo, al lado derecho voy a colocar 4 botones que son _Home_, _Nosotros_, _Servicios_ y _Contacto_.

|   |
| - |

```
<!-- Menú -->
<nav class="nav flex flex-wrap items-center justify-between px-4 bg-gray-800 px-20"> 
 <div class="flex flex-no-shrink items-center mr-6 py-3 text-grey-darkest">  
   <span class="font-semibold text-xl tracking-tight text-white">Mi Proyecto</span> 
    </div>  <input class="menu-btn hidden" type="checkbox" id="menu-btn">  
    <label class="menu-icon block cursor-pointer md:hidden px-2 py-4 relative select-none" for="menu-btn">    
    <span class="navicon bg-grey-darkest flex items-center relative"></span>  </label>
      <ul class="menu border-b md:border-none flex justify-end list-reset m-0 w-full md:w-auto">   
       <li class="border-t md:border-none">      
       <a href="/" class="block md:inline-block px-4 py-3 no-underline text-grey-darkest hover:text-grey-darker font-bold text-white ">Home</a>    </li>   
        <li class="border-t md:border-none">      <a href="/about/" class="block md:inline-block px-4 py-3 no-underline text-grey-darkest hover:text-grey-darker text-white ">Nosotros</a>    </li>    
        <li class="border-t md:border-none">      <a href="/blog/" class="block md:inline-block px-4 py-3 no-underline text-grey-darkest hover:text-grey-darker text-white ">Servicios</a>    </li>    
        <li class="border-t md:border-none">      <a href="/blog/" class="block md:inline-block px-4 py-3 no-underline text-grey-darkest hover:text-grey-darker text-white ">Contacto</a>    </li>  
        </ul>
        </nav> 
```

Entonces si abro el archivo en el navegador o en mi servidor, debo de ver el menú sin problemas:

#### Servicios Destacados

En esta sección voy a mostrar 4 servicios destacados, obviamente en la página _Servicios_ que crearé más adelante, alli mostraré todos los servicios. Para esta sección colocaré 4 servicios: Servicio 1, Servicio 2, Servicio 3 y Servicio 4. Cada servicio tiene una imagen, una descripción y un botón para leer más

```
 <!-- Servicios Destacados -->
 <div class="container ml-auto mr-auto flex flex-wrap items-start mt-8">  
 <div class="w-full pl-5 lg:pl-2 mb-4 mt-4">   
  <h1 class="text-3xl font-extrabold text-center"> Servicios Destacados </h1>  </div>
    <div class="w-full md:w-1/2 lg:w-1/4 pl-5 pr-5 mb-5 lg:pl-2 lg:pr-2">   
     <div class="bg-white rounded-lg m-h-64 p-2 transform hover:translate-y-2 hover:shadow-xl transition duration-300">      <figure class="mb-2">        <img src="assets/img/s1.png" alt="" class="h-64 ml-auto mr-auto" />      </figure>      
     <div class="rounded-lg p-4 flex flex-col">        
     <div>          <h5 class="text-2xl font-bold leading-none text-center"> Servicio 1 </h5>          <p class="mt-4"> Nulla blandit ac tortor a ullamcorper. Fusce dictum, quam at ornare finibus, leo erat lacinia urna, vitae interdum est lacus vel massa. Donec porttitor posuere lacus sit amet auctor. Fusce fringilla mauris ipsum, nec tempus odio porttitor a. Cras eu urna eget est egestas pulvinar. </p>       
      </div>        <div class="flex items-center mt-4">          <a href="#" class="font-bold text-orange-900">Leer más</a>         
       <button href="javascript:;" class="rounded-full bg-purple-900 text-white hover:bg-white hover:text-purple-900 hover:shadow-xl focus:outline-none w-10 h-10 flex ml-4 transition duration-300">            
       <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="stroke-current m-auto">             
        <line x1="12" y1="5" x2="12" y2="19"></line>              <line x1="5" y1="12" x2="19" y2="12"></line>            </svg>          </button>      
          </div>      
          </div>    
          </div> 
           </div>  
           <div class="w-full md:w-1/2 lg:w-1/4 pl-5 pr-5 mb-5 lg:pl-2 lg:pr-2">   
            <div class="bg-white rounded-lg m-h-64 p-2 transform hover:translate-y-2 hover:shadow-xl transition duration-300">     
             <figure class="mb-2">       
              <img src="assets/img/s2.png" alt="" class="h-64 ml-auto mr-auto" />      </figure>      <div class="rounded-lg p-4 flex flex-col">        <div>          <h5 class="text-2xl font-bold leading-none text-center"> Servicio 2 </h5>          <p class="mt-4"> Nulla blandit ac tortor a ullamcorper. Fusce dictum, quam at ornare finibus, leo erat lacinia urna, vitae interdum est lacus vel massa. Donec porttitor posuere lacus sit amet auctor. Fusce fringilla mauris ipsum, nec tempus odio porttitor a. Cras eu urna eget est egestas pulvinar. </p>        </div>        <div class="flex items-center mt-4">          <a href="#" class="font-bold text-orange-900">Leer más</a>          <button href="javascript:;" class="rounded-full bg-purple-900 text-white hover:bg-white hover:text-purple-900 hover:shadow-xl focus:outline-none w-10 h-10 flex ml-4 transition duration-300">            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="stroke-current m-auto">              <line x1="12" y1="5" x2="12" y2="19"></line>              <line x1="5" y1="12" x2="19" y2="12"></line>            </svg>          </button>        </div>      </div>    </div>  </div>  <div class="w-full md:w-1/2 lg:w-1/4 pl-5 pr-5 mb-5 lg:pl-2 lg:pr-2">    <div class="bg-white rounded-lg m-h-64 p-2 transform hover:translate-y-2 hover:shadow-xl transition duration-300">      <figure class="mb-2">        <img src="assets/img/s3.png" alt="" class="h-64 ml-auto mr-auto" />      </figure>      <div class="rounded-lg p-4 flex flex-col">        <div>          <h5 class="text-2xl font-bold leading-none text-center"> Servicio 3 </h5>          <p class="mt-4"> Nulla blandit ac tortor a ullamcorper. Fusce dictum, quam at ornare finibus, leo erat lacinia urna, vitae interdum est lacus vel massa. Donec porttitor posuere lacus sit amet auctor. Fusce fringilla mauris ipsum, nec tempus odio porttitor a. Cras eu urna eget est egestas pulvinar. </p>        </div>        <div class="flex items-center mt-4">          <a href="#" class="font-bold text-orange-900">Leer más</a>          <button href="javascript:;" class="rounded-full bg-purple-900 text-white hover:bg-white hover:text-purple-900 hover:shadow-xl focus:outline-none w-10 h-10 flex ml-4 transition duration-300">            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="stroke-current m-auto">              <line x1="12" y1="5" x2="12" y2="19"></line>              <line x1="5" y1="12" x2="19" y2="12"></line>            </svg>          </button>        </div>      </div>    </div>  </div>  <div class="w-full md:w-1/2 lg:w-1/4 pl-5 pr-5 mb-5 lg:pl-2 lg:pr-2">    <div class="bg-white rounded-lg m-h-64 p-2 transform hover:translate-y-2 hover:shadow-xl transition duration-300">      <figure class="mb-2">        <img src="assets/img/s4.png" alt="" class="h-64 ml-auto mr-auto" />      </figure>      <div class="rounded-lg p-4 flex flex-col">        <div>          <h5 class="text-2xl font-bold leading-none text-center"> Servicio 4 </h5>          <p class="mt-4"> Nulla blandit ac tortor a ullamcorper. Fusce dictum, quam at ornare finibus, leo erat lacinia urna, vitae interdum est lacus vel massa. Donec porttitor posuere lacus sit amet auctor. Fusce fringilla mauris ipsum, nec tempus odio porttitor a. Cras eu urna eget est egestas pulvinar. </p>        </div>        <div class="flex items-center mt-4">          <a href="#" class="font-bold text-orange-900">Leer más</a>          <button href="javascript:;" class="rounded-full bg-purple-900 text-white hover:bg-white hover:text-purple-900 hover:shadow-xl focus:outline-none w-10 h-10 flex ml-4 transition duration-300">            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="stroke-current m-auto">              <line x1="12" y1="5" x2="12" y2="19"></line>              <line x1="5" y1="12" x2="19" y2="12"></line>            </svg>          </button>        </div>      </div>    </div>  </div></div> 
```

Asimismo le he colocado un efecto de sombra, es decir cuando el usuario coloca el puntero del mouse sobre un servicio, se muestre una sombra que lo resalte. Igualmente, si voy al navegador, debería de ver los servicios destacados sin problema:

Ahora vamos a crear un formulario para que los usuarios se suscriban al boletín de novedades o newsletter.

#### Newsletter

Esta sección va tener un formulario para que el usuario escriba su correo y un botón para confirmar la suscripción.

|   |
| - |

```
 <!-- Newsletter --><div class="mx-auto max-w-7xl p-4">  <div class="w-full mb-4 mt-4">    <h1 class="text-3xl font-extrabold text-center"> Newsletter </h1>  </div>  <form method="post">    <div class="md:flex md:items-center mb-6">      <div class="md:w-1/2">        <label class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4" for="inline-full-name"> Email: </label>      </div>      <div class="md:w-2/3 mr-2">        <input class="appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="email" placeholder="micorreo@mail.com" required>      </div>      <div class="md:w-2/3">        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="submit"> Aceptar </button>      </div>    </div>  </form></div> 
```

De la misma manera, si voy al navegador debería de ver el formulario de suscripción al newsletter, sin problemas:

Bien y para terminar con la página principal, terminaré creando el Footer o pie de página para el sitio web, vamos con ello.

### Footer

Este elemento al igual que el Menú va a estar presente en todas las páginas del sitio web, en el simplemente colocaré un texto del nombre de mi proyecto, un código JavaScript que actualiza el año automáticamente (asi evitamos estar cambiando el año manualmente) y un texto que dice _Todos los derechos reservados_. Le pondré un fondo gris a todo el Footer.

|   |
| - |

```
 <!-- Footer --><footer class="footer-1 bg-gray-100 py-8 sm:py-12 text-center">  <div class="container mx-auto">    <p>©Mi Proyecto <script>        document.write(new Date().getFullYear())      </script>. Todos los derechos reservados. </p>  </div></footer> 
```

Asimismo, si voy al navegador, debería de ver el Footer sin problemas:

[![](https://blog.nubecolectiva.com/wp-content/uploads/2021/12/i6.jpg)](https://blog.nubecolectiva.com/wp-content/uploads/2021/12/i6.jpg)

Y eso es todo para la página Home o Principal. **Recuerda que en la última parte del tutorial colocaré todos los archivos del proyecto**, incluido el archivo _estilos.css_ en donde he creado mis propios estilos personalizados (Si bien estoy usando clases nativas de Tailwind CSS 3 para aplicar los estilos, también he creado mis propios estilos CSS. ). Asimismo colocaré las imágenes y otros archivos que use en este tutorial.

**Ten Paciencia, lo que quiero es que** conozcas bien como se crea este proyecto y no llenarte el capitulo de mucho contenido porque te puedes marear y no tendrás un óptimo aprendizaje.&#x20;

### Nota (s)

* En la siguiente parte de este tutorial, vamos a crear el contenido de la página Nosotros.
* No olvides que debemos usar la Tecnología para hacer cosas Buenas por el Mundo.&#x20;

Síguenos en nuestras Redes Sociales para que no te pierdas nuestros próximos contenidos.
