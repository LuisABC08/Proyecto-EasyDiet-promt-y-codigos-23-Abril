Como desarrollador de software, el ecosistema de **Firebase CLI** es fundamental para automatizar el despliegue y la configuración de tus proyectos de Flutter. Aquí tienes la guía técnica paso a paso para preparar tu entorno en Windows.

---

## 1. Requisito Previos: Node.js y NPM
Para usar Firebase CLI, necesitamos el entorno de ejecución de JavaScript **Node.js**, el cual incluye automáticamente **npm** (Node Package Manager).

### Cómo verificar si ya los tienes
Abre una terminal (CMD o PowerShell) y escribe:
```powershell
node -v
npm -v
```
> **Nota:** Yo utilizo y recomiendo la versión **LTS (Long Term Support)**, actualmente la **v20.x** o superior, ya que garantiza estabilidad para herramientas de desarrollo como Firebase.

---

## 2. Instalación de Node.js de manera Global (Windows)

Si no recibiste una versión en el paso anterior, sigue este procedimiento:

1.  **Descarga:** Ve al sitio oficial [nodejs.org](https://nodejs.org/) y selecciona la versión **LTS**.
2.  **Ejecución:** Abre el instalador `.msi`.
3.  **Configuración Crucial:** * Acepta los términos.
    * En la pantalla de "Custom Setup", asegúrate de que la opción **"Add to PATH"** esté seleccionada (esto es lo que permite que sea "Global").
    * Marca la casilla que ofrece instalar "Tools for Native Modules" (esto instala Chocolatey y herramientas de C++ necesarias para algunos paquetes).
4.  **Finalización:** Haz clic en *Install* y, al terminar, **reinicia tu terminal** o tu PC para que los cambios en las variables de entorno surtan efecto.

---

## 3. Instalación de Firebase CLI

Una vez que `npm` funciona, instalamos las herramientas de Firebase para que estén disponibles en todo tu sistema.

### Comando de Instalación Global
En tu terminal, ejecuta el siguiente comando. El flag `-g` indica que la instalación es **global**:

```powershell
npm install -g firebase-tools
```



---

## 4. Comandos de Firebase: Acceso y Configuración

Ahora que tienes las herramientas, debes vincular tu terminal con tu identidad de Google.

### Cómo acceder con tu Cuenta de Google
Ejecuta el siguiente comando para iniciar el flujo de autenticación:

```powershell
firebase login
```

* **¿Qué sucederá?** Se abrirá una ventana en tu navegador predeterminado.
* **Acción:** Selecciona tu cuenta de Google (la misma que usas en la consola de Firebase).
* **Confirmación:** Una vez aceptado, la terminal mostrará un mensaje de éxito: `Success! Logged in as user@gmail.com`.

---

## 5. Integración con Flutter (FlutterFire CLI)

Para que tu proyecto de Flutter "hable" con Firebase de forma profesional, no basta con `firebase-tools`; usamos un complemento llamado **FlutterFire CLI**.

### Instalación de FlutterFire
```powershell
dart pub global activate flutterfire_cli
```

### Cómo configurar tu proyecto
Dentro de la carpeta raíz de tu proyecto `CRUDEasyDiet`, ejecuta:

```powershell
flutterfire configure
```

**Este comando hace la magia:**
1.  Te permite seleccionar tu proyecto de Firebase creado en la consola.
2.  Te pregunta para qué plataformas (Android, iOS, Web).
3.  **Genera automáticamente** el archivo `firebase_options.dart` en tu carpeta `lib/`, evitándote configurar manualmente archivos JSON o Plist.

---

## 6. Resumen de comandos útiles (`firebase-tools`)

| Comando | Propósito |
| :--- | :--- |
| `firebase projects:list` | Muestra todos tus proyectos activos en Firebase. |
| `firebase logout` | Cierra la sesión actual de la cuenta de Google. |
| `firebase help` | Lista todos los comandos disponibles y su sintaxis. |
| `firebase init` | Inicia la configuración de servicios específicos (Hosting, Functions, etc.) en un directorio. |

¿Deseas que profundicemos en cómo usar el comando `flutterfire configure` para vincular específicamente tu base de datos de Firestore al proyecto?
