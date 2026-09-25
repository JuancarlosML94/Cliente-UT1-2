### 1. Análisis de red y modelo de renderizado

En Spotify, el HTML inicial tiene un tamaño de **44,2 kB**, mientras que los recursos JavaScript llegan aproximadamente a **10 MB**. Al revisar el HTML, vemos que contiene principalmente la estructura inicial y que gran parte de la aplicación se carga mediante JavaScript. Por ello, podemos decir que utiliza principalmente **Client-Side Rendering (CSR)**.

**Capturas:** `spotify.png` y `spotify_js.png`.

### 2. Rendimiento y motor JavaScript

Durante la grabación de rendimiento encontramos los eventos **Parse HTML**, **Compile Script** y **Evaluate Script**. El navegador primero procesa el HTML, después prepara/compila el código JavaScript y finalmente lo ejecuta. En Chrome este proceso lo realiza el motor **V8**, que utiliza técnicas de compilación y optimización para mejorar el rendimiento.

**Capturas:** `parse_html.png`, `compile_script.png` y `evaluate_script.png`.

### 3. Sandbox y seguridad

En la consola comprobamos que el navegador permite ejecutar JavaScript, pero bloquea el acceso directo a archivos del ordenador. Al intentar acceder a `C:/Windows/system.ini`, Chrome mostró **“Not allowed to load local resource”**. Esto demuestra la función del **Sandbox**, que limita el acceso de una página web a los recursos del equipo para mejorar la seguridad.

**Capturas:** `console.png` y `sandbox_file.png`.

### 4. Bloqueo y scripts de gran tamaño

En YouTube encontramos un archivo JavaScript de **1.996 KB**, aproximadamente 2 MB. Si este código se ejecutara de forma síncrona, podría bloquear durante su ejecución otras tareas del navegador y hacer que la página respondiera más lentamente. El uso de ejecución asíncrona y basada en eventos ayuda a evitar estos bloqueos y mejora la experiencia del usuario.

**Captura:** `script_mayor_1MB.png`.
