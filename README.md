# gemma3
gemma 3 API

**Resumen del Proyecto y Tareas Pendientes**

**Objetivo Principal:**
Crear una aplicación móvil de IA conversacional que funcione de forma local (sin internet). Se ha decidido usar el framework multiplataforma Flutter para poder apuntar a Android y, eventualmente, a iOS.

**Arquitectura Decidida:**
- **Framework:** Flutter con el lenguaje Dart.
- **Plataforma de Desarrollo Inicial:** Windows, para crear y probar la versión de Android.
- **Modelo de IA:** `google/gemma-2b-it` (Gemma 2B), que se ejecutará localmente en el dispositivo.
- **Framework de IA Móvil:** TensorFlow Lite (`.tflite`).
- **Voz a Texto y Texto a Voz:** Se usarán las capacidades nativas de la plataforma (Android en este caso).

**Estado Actual:**
- Se ha definido el plan de acción completo.
- El usuario está a punto de configurar su entorno de desarrollo en su máquina con Windows.

**Tareas Pendientes (En orden):**

1.  **Configurar el Entorno (Tarea del Usuario):** El usuario debe seguir las instrucciones del archivo `instrucciones_configuracion_flutter.txt` para instalar Flutter, Android Studio y sus dependencias. El objetivo es que el comando `flutter doctor` se ejecute sin errores para la "Android toolchain".

2.  **Convertir el Modelo (Nuestra Próxima Tarea Conjunta):** Una vez el entorno esté listo, ejecutaremos el script `convert_model_to_tflite.py` para descargar el modelo Gemma 2B y convertirlo al formato `.tflite` que necesita la app.

3.  **Crear el Proyecto Flutter:** Iniciaremos un nuevo proyecto de Flutter.

4.  **Desarrollar la App:** Escribiremos el código en Dart para la interfaz de usuario, la lógica de la app y la integración con el modelo `.tflite`.

Pasos para configurar tu entorno de desarrollo Flutter en Windows:

**Tarea 1: Instalar el Software Necesario**

1.  **Instalar el SDK de Flutter:**
    *   Ve a la página oficial: https://docs.flutter.dev/get-started/install/windows
    *   Descarga el archivo ZIP y descomprímelo en una ubicación permanente (ej: C:\flutter).
    *   Sigue las instrucciones de la web para añadir la carpeta `C:\flutter\bin` a tu variable de entorno `Path` del sistema. Esto es crucial.

2.  **Instalar Android Studio:**
    *   Descárgalo desde el sitio oficial de Android: https://developer.android.com/studio
    *   Durante la instalación, asegúrate de que los componentes "Android SDK", "Android SDK Command-line Tools", y "Android SDK Build-Tools" estén seleccionados.

3.  **Verificar la Instalación con Flutter Doctor:**
    *   Abre una **nueva** terminal (CMD o PowerShell) para que reconozca los cambios en el `Path`.
    *   Ejecuta el comando: `flutter doctor`
    *   La herramienta te dirá si falta algo. Es muy común que te pida aceptar las licencias de Android. Para ello, ejecuta el comando que te sugiera, que suele ser: `flutter doctor --android-licenses`.
    *   Sigue ejecutando `flutter doctor` hasta que la sección "Android toolchain" aparezca con un tic verde [✓].

4.  **Instalar un Editor de Código (Recomendado):**
    *   Descarga e instala Visual Studio Code (VS Code).
    *   Abre VS Code, ve a la pestaña de Extensiones (el icono de los cuadrados en la barra lateral).
    *   Busca e instala las extensiones oficiales de `Flutter` y `Dart`.


**Tarea 2: Convertir el Modelo (Después de la Tarea 1)**

Una vez que `flutter doctor` esté contento, el siguiente paso será ejecutar el script de Python `convert_model_to_tflite.py` para preparar nuestro modelo de IA.

