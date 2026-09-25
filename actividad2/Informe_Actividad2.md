# Actividad 2. defer, async y módulos

### 1. Script tradicional en `<head>`

Al colocar el script dentro del `<head>`, se ejecuta antes de que el navegador haya creado el `<h1>`. Por eso `getElementById('titulo')` devuelve `null` y aparece un error. El título se mantiene en **“Hola”**.

**Captura:** `caso_a_error.png`.

### 2. Script tradicional antes de `</body>`

Al colocar el script justo antes de cerrar el `body`, el navegador ya ha creado el `<h1>`. Por este motivo el script encuentra el elemento y cambia correctamente el título.

**Captura:** `caso_b_correcto.png`.

### 3. Script con `async`

Con `async`, el archivo JavaScript se descarga mientras se procesa el HTML y se ejecuta cuando termina de cargarse. En nuestra prueba se ejecutó cuando el `<h1>` ya estaba disponible, por lo que el título cambió correctamente.

**Captura:** `caso_c_async.png`.

### 4. Script con `defer`

Con `defer`, el navegador puede descargar el script mientras procesa el HTML, pero espera a que el documento haya sido procesado antes de ejecutarlo. Por eso el script encuentra el `<h1>` y cambia el título correctamente.

**Captura:** `caso_d_defer.png`.

### 5. Módulos ES

Con `type="module"`, al abrir el archivo directamente mediante `file://`, Chrome bloqueó la carga del JavaScript por la política de seguridad CORS. Al probarlo mediante `localhost`, el módulo se ejecutó correctamente y cambió el título.

**Captura:** `caso_e_module.png`.

### 6. Análisis de rendimiento

En la grabación de Performance encontramos **Parse HTML** con una duración de 99 μs y **Evaluate Script** con una duración de 6,52 ms. Esto muestra que el navegador procesa el HTML y después ejecuta el código JavaScript. En esta grabación no apareció el evento **Compile Script**.

**Capturas:** `performance_parse_html.png` y `performance_evaluate_script.png`.
