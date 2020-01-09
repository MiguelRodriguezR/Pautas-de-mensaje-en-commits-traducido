## <a name="commit"></a> GUÍA DE MENSAJES EN COMMITS

Existen algunas reglas muy precisas sobre cómo se pueden formatear nuestros mensajes git commit. Esto lleva a **más
mensajes legibles** que son fáciles de seguir cuando se mira a través del **historial del proyecto**. Pero también,
Usamos los mensajes de commit de git para **generar el registro de cambios**

### Formato de mensaje de un Commit
Cada mensaje de commit consta de un **encabezado**, un **cuerpo** y un **pie de página**. El encabezado tiene un formato especial
que incluye un **type**, un **scope** y un **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

El **encabezado** es obligatorio y el **scope** del encabezado es opcional.

¡Cualquier línea del mensaje del commit no puede tener más de 100 caracteres! Esto permite que el mensaje sea más fácil.
para leer en GitHub, así como en varias herramientas de git.

El pie de página debe contener una [referencia de cierre a un problema](https://help.github.com/articles/closing-issues-via-commit-messages/), si corresponde.

Ejemplos: [algunos ejemplos serian](https://github.com/angular/angular/commits/master)

```
docs(changelog): se actualizó el registro de cambios a beta.5
```

```
fix(release): se soluciono la necesidad de depender de los últimos rxjs y zone.js

La versión en nuestro package.json se copia a la que publicamos, y los usuarios ya no las requieren
```

### Revertir
Si el commit revierte un commit anterior, debe comenzar con `revert:`, seguido del encabezado del commit revertido. En el cuerpo debería decir: `Esto revierte commit <hash> .`, donde el hash es el SHA del commit que se revierte.

### Type
Debe ser uno de los siguientes:

* **build**: Cambios que afectan el sistema de compilación o dependencias externas (ejemplos de alcance: gulp, broccoli, npm)
* **ci**: Cambios en nuestros archivos de configuración de CI y scripts (ejemplos de ámbitos: Circle, BrowserStack, SauceLabs)
* **docs**: solo la documentación cambia
* **feat**: cuando se agrega una nueva característica
* **fix**: cuando se corrige un error
* **perf**: cuando hay un cambio de código que mejora el rendimiento
* **refactor**: cuando hay un cambio de código que no corrige un error ni agrega una función
* **style**: cambios que no afectan el significado del código (espacios en blanco, formato, puntos y comas faltantes, etc.)
* **test**: Agregar pruebas faltantes o corregir pruebas existentes

### Scope
El scope debe ser el nombre del paquete npm afectado (tal como lo percibe la persona que lee el registro de cambios generado a partir de los mensajes del commit).

La siguiente es la lista de ejemplos de scope:

* **animations**
* **common**
* **compiler**
* **compiler-cli**
* **core**
* **elements**
* **forms**
* **http**
* **language-service**
* **platform-browser**
* **platform-browser-dynamic**
* **platform-server**
* **platform-webworker**
* **platform-webworker-dynamic**
* **router**
* **service-worker**
* **upgrade**
* **zone.js**

### Subject
El subject contiene una breve descripción del cambio que se hizo:

* no capitalice la primera letra
* sin punto (.) al final

### Pie de página
El pie de página debe contener cualquier información sobre **cambios de ulima hora** y también es el lugar para que
haga referencia a los problemas de GitHub que este commit **cierra**.