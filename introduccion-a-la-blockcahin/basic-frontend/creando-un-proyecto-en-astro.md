# Creando un proyecto en Astro

```
npm create astro@latest
```

<figure><img src="../../.gitbook/assets/nombredelgif (1).gif" alt=""><figcaption></figcaption></figure>

Luego de lanzar el comando Astro empieza a crear el proyecto y nos va haciendo preguntas  donde  le decimos  a Astro que instale las dependencias,  luego le damos la ruta donde queremos que quede ubicado el proyecto, posteriormente elegimos la plantilla con la que queremos arrancar nuestro poryecto.



Astro posee un servidor de desarrollo que tiene todo lo que necesitas para desarrollar tu proyecto. El comando `astro dev` iniciará el servidor de desarrollo local para que veas tu nuevo proyecto en acción por primera vez.

Cada plantilla de inicio posee un script preconfigurado que ejecutará `astro dev` por ti. Utiliza tu gestor de paquetes favorito para ejecutar este comando e iniciar el servidor de desarrollo de Astro.



```
npm run dev
```

¡Si todo marcha bien, Astro deberá servir tu proyecto localmente en [http://localhost:3000](http://localhost:3000)!

Astro escuchará cualquier cambio en la carpeta `src/` y actualizará automáticamente tu proyecto. De esta forma, no será necesario reiniciar el servidor local durante el desarrollo.

Si no es posible abrir el proyecto en el navegador, regresa a la terminal donde has ejecutado el comando `dev` y chequea si ha ocurrido algún error o si tu proyecto está siendo servido en una URL diferente a la mencionada anteriormente.

<figure><img src="../../.gitbook/assets/nombredelgif2.gif" alt=""><figcaption></figcaption></figure>

Ahora tenemos el proyecto creado y corriendo el  localhost, para  empezar a alterar el código, podemos hacer el reto que nos ponen en la plantilla, "Para empezar, abre el directorio src/pages en tu proyecto. Reto de código: Modifica el mensaje "Bienvenido a Astro" anterior."

Este es el código que tenemos en el archivo index.astro, que funcionaria cómo en html funciona el index.html

Si observamos bien tenemos una sintaxis muy similar a html y css,  ahora nos vamos a la linea 8 del archivo y cambiamos el contenido de la etiqueta \<h1>

````
```astro
---
import Layout from '../layouts/Layout.astro';
import Card from '../components/Card.astro';
---

<Layout title="Welcome to Astro.">
	<main>
		<h1>Welcome to <span class="text-gradient">Astro</span></h1>
		<p class="instructions">
			To get started, open the directory <code>src/pages</code> in your project.<br />
			<strong>Code Challenge:</strong> Tweak the "Welcome to Astro" message above.
		</p>
		<ul role="list" class="link-card-grid ">
			<Card
				href="https://docs.astro.build/"
				title="Documentation"
				body="Learn how Astro works and explore the official API docs."
			/>
			<Card
				href="https://astro.build/integrations/"
				title="Integrations"
				body="Supercharge your project with new frameworks and libraries."
			/>
			<Card
				href="https://astro.build/themes/"
				title="Themes"
				body="Explore a galaxy of community-built starter themes."
			/>
			<Card
				href="https://astro.build/chat/"
				title="Community"
				body="Come say hi to our amazing Discord community. ❤️"
			/>
		</ul>
	</main>
</Layout>

<style>
	main {
		margin: auto;
		padding: 1.5rem;
		max-width: 60ch;
	}
	h1 {
		font-size: 3rem;
		font-weight: 800;
		margin: 0;
	}
	.text-gradient {
		background-image: var(--accent-gradient);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		background-size: 400%;
		background-position: 0%;
	}
	.instructions {
		line-height: 1.6;
		margin: 1rem 0;
		border: 1px solid rgba(var(--accent), 25%);
		background-color: white;
		padding: 1rem;
		border-radius: 0.4rem;
	}
	.instructions code {
		font-size: 0.875em;
		font-weight: bold;
		background: rgba(var(--accent), 12%);
		color: rgb(var(--accent));
		border-radius: 4px;
		padding: 0.3em 0.45em;
	}
	.instructions strong {
		color: rgb(var(--accent));
	}
	.link-card-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(24ch, 1fr));
		gap: 1rem;
		padding: 0;
	}
</style>

```
````

<figure><img src="../../.gitbook/assets/nombredelgif3.gif" alt=""><figcaption></figcaption></figure>

