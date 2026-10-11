# SENSI AI NEON — Proyecto Android

Este proyecto empaqueta la versión web de SENSI AI NEON dentro de una app Android usando WebView.

## Qué incluye
- Interfaz web negra y verde neón.
- Ajustes de sensibilidad de 0 a 200.
- Generador heurístico de configuración inicial.
- Guardado local de perfiles con localStorage.
- Enlaces a las noticias oficiales de Free Fire.
- La app no cambia el DPI ni modifica Free Fire.

## Requisitos para compilar
- Android Studio actualizado.
- JDK 17 (Android Studio puede administrar el JDK).
- Conexión a internet la primera vez para descargar Gradle y dependencias.
- SDK Android 35 instalado desde SDK Manager.

## Cómo abrir y compilar
1. Descomprime `SensiAINeonAndroid.zip`.
2. Abre Android Studio.
3. Pulsa **Open** y selecciona la carpeta `SensiAINeonAndroid` (la que contiene `settings.gradle`).
4. Espera a que termine **Gradle Sync**. Si pide instalar Android SDK 35 o componentes de compilación, acepta.
5. Para probar en un teléfono: activa Opciones de desarrollador y Depuración USB, conecta el teléfono y pulsa **Run ▶**.
6. Para crear un APK: menú **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
7. Android Studio mostrará un aviso con el enlace **locate** para encontrar el APK. Normalmente se crea en `app/build/outputs/apk/debug/app-debug.apk`.

## Instalar el APK
Copia el APK al teléfono y ábrelo desde Archivos/Descargas. Si Android pregunta, permite instalar aplicaciones desde esa fuente solo para la app que estés usando y continúa. Después puedes desactivar ese permiso.

## Limitaciones de esta primera versión
- Este proyecto contiene el código fuente; el APK no se ha compilado ni probado en un dispositivo físico desde aquí.
- La página puede leer solo datos que Android/WebView expone al navegador. No detecta de forma fiable el estado físico de la pantalla, los procesos privados, el FPS exacto de Free Fire ni el DPI real del sistema.
- El guardado de perfiles funciona localmente en el almacenamiento web de la app. La importación/exportación de archivos puede variar en WebView; si no funciona, usa la versión HTML en un navegador compatible.
- Los enlaces web oficiales se abren en el navegador externo.
- La sensibilidad se mantiene limitada a 0–200 en los seis controles. Las sugerencias son cálculos heurísticos, no una IA conectada ni una garantía de rendimiento.

## Versiones de herramientas
Configuración inicial: Android Gradle Plugin 8.9.2, Gradle 8.11.1 recomendado, Java 17, compileSdk 35 y minSdk 23.


## Compilar desde solo un celular (GitHub Actions)
También incluí `.github/workflows/build-apk.yml` para que GitHub compile el APK en la nube.

1. En el navegador del celular, entra a GitHub e inicia sesión o crea una cuenta.
2. Crea un repositorio nuevo, por ejemplo `SensiAINeonAndroid`.
3. Sube todos los archivos y carpetas que vienen dentro del ZIP, incluyendo la carpeta oculta `.github`. Si el cargador móvil no permite subir carpetas fácilmente, usa la opción de subir archivos del sitio en modo escritorio o sube el proyecto desde una computadora prestada.
4. En el repositorio, abre la pestaña **Actions** y el flujo **Build SENSI AI NEON APK**. Pulsa **Run workflow** si no arrancó automáticamente al subir los archivos.
5. Espera a que termine en verde. Abre la ejecución completada, baja a **Artifacts** y descarga `SENSI-AI-NEON-debug-apk`.
6. Descomprime el archivo de artifacts descargado; dentro estará `app-debug.apk`. Tócalo para instalarlo.

GitHub Actions requiere una cuenta y conexión a internet. No publiques contraseñas, claves privadas ni información personal en el repositorio. Un APK debug sirve para pruebas; para distribuirlo públicamente conviene configurar firma de release.
