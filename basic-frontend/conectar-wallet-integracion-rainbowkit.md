# Conectar wallet - Integración Rainbowkit

## Añadir-conexión-a-billetera

### Uso del botón Conectar

Ahora que hemos empaquetado nuestra aplicación con los componentes `WagmiConfig` y `RainbowKitProvider`, podemos usar la biblioteca de ganchos wagmi y el componente `ConnectButton` de RainbowKit para permitir a los usuarios conectar su billetera e informar al usuario que su billetera está conectada.

En `/components/Navbar.js`, podemos importar el componente `ConnectButton` de RainbowKit y los ganchos `useAccount` y `useDisconnect` de wagmi.

```javascript
import { ConnectButton } from "@rainbow-me/rainbowkit";
import { useAccount, useDisconnect } from "wagmi";
```

Usaremos el gancho `useAccount` para acceder a la billetera conectada, si existe, y el gancho `useDisconnect` para desconectar la billetera conectada actualmente.

```javascript
export default function Navbar() {
    const { data: account } = useAccount();
    const { disconnect } = useDisconnect();
```

En nuestra `Navbar`, podemos verificar el estado de conexión de la billetera del usuario. Si la billetera del usuario está conectada, visualizaremos un botón que muestra la dirección de la billetera del usuario y activa un menú desplegable. De lo contrario, si la billetera del usuario no está conectada, visualizaremos el botón "Conectar billetera" de RainbowKit. Podemos agregar este botón después del botón Crear evento.

```javascript
    </Link>
    {account ? (
        <Navmenu account={account} disconnect={() => disconnect()} />
    ) : (
        <ConnectButton />
    )}
</div>
```

Así es como su archivo Navbar.js se debe observar:

```javascript
import { useState, useEffect } from "react";
import Link from "next/link";
import Navmenu from "./Navmenu";
import { ConnectButton } from "@rainbow-me/rainbowkit";
import { useAccount, useDisconnect } from "wagmi";

export default function Navbar() {
  const { data: account } = useAccount();
  const { disconnect } = useDisconnect();
  const [mounted, setMounted] = useState(false);

  useEffect(() => {
    setMounted(true);
  }, []);

  return (
    mounted && (
      <header className="bg-white border-b-2 border-gray-100">
        <nav
          className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8"
          aria-label="Top"
        >
          <div className="w-full py-6 flex flex-wrap items-center justify-between border-b border-indigo-500 lg:border-none">
            <div className="flex items-center">
              <Link href="/">
                <a>web3rsvp</a>
              </Link>
            </div>
            <div className="ml-10 space-x-4 flex items-center">
              <Link href="/create-event">
                <a className="inline-flex items-center px-4 py-2 border border-transparent text-sm font-medium rounded-md text-indigo-700 border border-indigo-100 hover:bg-indigo-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                  Create Event
                </a>
              </Link>
              {account ? (
                <Navmenu account={account} disconnect={() => disconnect()} />
              ) : (
                <ConnectButton />
              )}
            </div>
          </div>
        </nav>
      </header>
    )
  );
}
```

Pasamos el objeto de cuenta y la función de desconexión a nuestro componente Navmenu. Los próximos dos pasos **ya están hechos para usted.** En `/components/Navmenu.js`, notará que mostramos la dirección de la billetera de conexión de la siguiente manera:

```javascript
<p className="text-ellipsis overflow-hidden">{account.address}</p>
```

También permitimos que los usuarios puedan desconectar sus billeteras:

```javascript
<a
  onClick={disconnect}
  className={joinClassNames(
    account ? "bg-gray-100 text-gray-900" : "text-gray-700",
    "block px-4 py-2 text-sm cursor-pointer"
  )}
>
  Log Out
</a>
```

A lo largo de nuestra dApp, verificamos la conexión de la billetera del usuario para renderizar condicionalmente la interfaz de usuario usando el gancho `useAccount` de wagmi.

Después de una configuración e importación exitosas, al hacer clic en el botón de conexión, debe esperar una interfaz de usuario como esta:



Escritoras: [Sarah Z](https://twitter.com/haegeez), [Busayo](https://twitter.com/AmoweO), Traductoras: [Dami](https://twitter.com/dakitidami), [Brenda](https://twitter.com/engineerbrenda), [Caro Meneses](https://twitter.com/carmedinat)
