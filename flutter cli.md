¡Hola! Configurar las herramientas de Firebase para Flutter es el primer gran paso para darle superpoderes a tu aplicación. En 2026, el proceso sigue siendo bastante directo, pero hay un par de detalles clave sobre las versiones de Node.js que debes cuidar.

Aquí tienes la guía completa para dejar tu entorno listo en Windows.

---

## 1. Verificación de Node.js y npm

Antes de instalar nada, debemos saber si ya tienes las herramientas en tu sistema.

* **Comandos de verificación:**
    Abre una terminal (PowerShell o Símbolo del Sistema) y escribe:
    ```powershell
    node -v
    npm -v
    ```
* **¿Qué versión utilizar?**
    Para abril de 2026, te recomiendo usar la versión **Node.js 22.x (LTS)** o superior. Evita la versión 20.x si es posible, ya que su soporte extendido finaliza este mes. **npm** se instala automáticamente junto con Node.js.



---

## 2. Instalación paso a paso de Node.js y npm

Si los comandos anteriores te dieron un error de "comando no reconocido", sigue estos pasos:

1.  **Descarga:** Ve al sitio oficial [nodejs.org](https://nodejs.org/).
2.  **Elige LTS:** Descarga el instalador `.msi` para Windows de la versión **LTS** (Long Term Support). Es la más estable para desarrollo con Flutter.
3.  **Ejecuta el instalador:** Sigue el asistente ("Next", "Next"...).
4.  **Punto Crítico (PATH):** Asegúrate de que la opción **"Add to PATH"** esté seleccionada (normalmente lo está por defecto). Esto permite que puedas usar `npm` desde cualquier carpeta.
5.  **Herramientas adicionales:** Si el instalador te pregunta si quieres instalar "Tools for Native Modules" (como Chocolatey o Python), puedes marcarlo, aunque para Firebase CLI no es estrictamente obligatorio.



---

## 3. Instalación de Firebase CLI de manera global

Una vez que tengas npm funcionando, instalaremos las herramientas de Firebase. El término "global" significa que el comando `firebase` estará disponible en cualquier proyecto de tu PC.

Ejecuta este comando en tu terminal:
```powershell
npm install -g firebase-tools
```
> **Tip:** El parámetro `-g` es lo que indica la instalación global. Si olvidas ponerlo, solo funcionará en la carpeta donde estés parado en ese momento.

---

## 4. Comandos básicos y acceso

Ahora que tienes las **firebase-tools** instaladas, veamos cómo usarlas para conectar tu cuenta y tu app de Flutter.

### a) Cómo usar `firebase-tools`
Las "tools" se invocan simplemente con la palabra `firebase`. Aquí tienes los comandos más útiles para empezar:

* **Verificar la instalación:**
    `firebase --version` (Te dirá qué versión de las herramientas tienes).
* **Ver tus proyectos:**
    `firebase projects:list` (Muestra todos los proyectos que tienes creados en la consola de Firebase).
* **Ayuda:**
    `firebase help` (Por si olvidas algún comando).

### b) Cómo acceder a Firebase con tu cuenta de Google
Este es el paso donde vinculas tu terminal con tu identidad de desarrollador:

1.  En la terminal, escribe:
    ```powershell
    firebase login
    ```
2.  **Interacción:** La terminal te preguntará si quieres permitir que Firebase recopile información de error (puedes decir `Y` o `n`).
3.  **Navegador:** Se abrirá automáticamente una ventana en tu navegador predeterminado.
4.  **Selección de cuenta:** Elige tu cuenta de Google, revisa los permisos y haz clic en **"Permitir"**.
5.  **Éxito:** Verás un mensaje en el navegador que dice "Firebase CLI Login Successful". Ya puedes cerrar esa pestaña y volver a tu terminal.



---

### Un extra para Flutter:
Como estás trabajando con Flutter, una vez que tengas el CLI de Firebase, te sugiero instalar el **FlutterFire CLI** (que corre sobre Dart) para configurar automáticamente tus archivos `firebase_options.dart`:

```powershell
dart pub global activate flutterfire_cli
flutterfire configure
```

¿Tienes ya algún proyecto creado en la consola de Firebase o prefieres que te ayude a crear uno nuevo desde la terminal?
