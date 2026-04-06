Guía de Instalación — Snyk Code (SAST)
Show Image
Show Image
Show Image
Show Image
Guía paso a paso para instalar y configurar Snyk Code como herramienta SAST (Static Application Security Testing) en IntelliJ IDEA y Visual Studio Code / Cursor.

📋 Tabla de contenidos

¿Qué es Snyk Code?
Requisitos previos
Instalación en IntelliJ IDEA
Instalación en Visual Studio Code / Cursor
Primer escaneo
Interpretación de resultados
Severidades en Snyk


🔍 ¿Qué es Snyk Code?
Snyk Code es una herramienta de análisis estático de seguridad (SAST) que escanea el código fuente de tu proyecto en busca de vulnerabilidades sin necesidad de ejecutar la aplicación.
A diferencia de otras herramientas, Snyk Code:

Analiza el flujo de datos entre funciones para detectar vulnerabilidades reales
Integra el escaneo directamente en el IDE — resultados en tiempo real mientras escribes
Cubre múltiples lenguajes: Kotlin, Java, Python, JavaScript, Dart, entre otros
Clasifica los hallazgos por severidad: Critical, High, Medium, Low
Mapea cada vulnerabilidad a su CWE y OWASP correspondiente


✅ Requisitos previos
Antes de instalar el plugin necesitas:

Cuenta Snyk — regístrate gratis en snyk.io

El plan gratuito incluye escaneo SAST ilimitado en proyectos personales.


Git instalado — Snyk lo usa para identificar el proyecto

bash   git --version

IDE compatible

IntelliJ IDEA 2021.1 o superior (Community o Ultimate)
Visual Studio Code 1.60 o superior / Cursor




🧠 Instalación en IntelliJ IDEA
Paso 1 — Abrir el Marketplace de plugins

Abre IntelliJ IDEA
Ve a File → Settings (Windows/Linux) o IntelliJ IDEA → Preferences (macOS)
En el panel izquierdo selecciona Plugins
Haz clic en la pestaña Marketplace

Show Image

Paso 2 — Buscar e instalar Snyk

En la barra de búsqueda escribe Snyk
Selecciona el plugin Snyk Security (publicado por Snyk Ltd.)
Haz clic en Install
Acepta los términos si se solicitan
Haz clic en Restart IDE cuando finalice la instalación

Show Image

Paso 3 — Autenticarse con Snyk

Una vez reiniciado el IDE, aparecerá el panel de Snyk en la barra lateral izquierda
Haz clic en el ícono de Snyk 🐝
Selecciona Connect IDE to Snyk
Se abrirá el navegador para autenticarte con tu cuenta de Snyk
Inicia sesión con Google, GitHub o correo/contraseña
Autoriza el acceso al IDE cuando el navegador lo solicite
Regresa al IDE — deberías ver el mensaje "Authenticated"

Show Image

Paso 4 — Configurar el escaneo

En el panel de Snyk haz clic en el ícono de ⚙️ Settings
Asegúrate de que las siguientes opciones estén activas:

✅ Snyk Code (análisis SAST del código propio)
✅ Snyk Open Source (análisis de dependencias)


Haz clic en Apply

Show Image

Paso 5 — Ejecutar el primer escaneo

Abre tu proyecto en IntelliJ
En el panel de Snyk haz clic en ▶ Run Scan
Espera a que el escaneo finalice (puede tardar 30–60 segundos dependiendo del tamaño del proyecto)
Los resultados aparecerán clasificados por severidad en el panel

Show Image

💻 Instalación en Visual Studio Code / Cursor
Paso 1 — Abrir el panel de extensiones

Abre VS Code o Cursor
Haz clic en el ícono de Extensiones en la barra lateral izquierda (o presiona Ctrl+Shift+X)

Show Image

Paso 2 — Buscar e instalar Snyk

En la barra de búsqueda escribe Snyk Security
Selecciona la extensión Snyk Security (publicada por Snyk)
Haz clic en Install
Espera a que finalice la instalación — no requiere reinicio

Show Image

Paso 3 — Autenticarse con Snyk

Aparecerá el ícono de Snyk 🐝 en la barra lateral izquierda
Haz clic en él para abrir el panel
Selecciona Connect VS Code to Snyk
Se abrirá el navegador para autenticarte
Inicia sesión con tu cuenta de Snyk
Autoriza el acceso y regresa al IDE
Verás el mensaje "Authenticated successfully"

Show Image

Paso 4 — Configurar el escaneo

Haz clic en el ícono de ⚙️ dentro del panel de Snyk
Activa las siguientes opciones:

✅ Snyk Code Security issues — vulnerabilidades en código propio (SAST)
✅ Open Source Security issues — vulnerabilidades en dependencias


Guarda la configuración

Show Image

Paso 5 — Ejecutar el escaneo

Abre tu proyecto en VS Code / Cursor
En el panel de Snyk haz clic en ▶ Run Scan o el botón de refrescar 🔄
El escaneo iniciará automáticamente
Los resultados aparecerán organizados por archivo y severidad

Show Image

🚀 Primer escaneo
Una vez autenticado e instalado el plugin, Snyk escanea automáticamente cuando:

Abres un proyecto por primera vez
Guardas un archivo (Ctrl+S)
Haces clic manualmente en Run Scan

Los resultados se muestran en dos categorías:
CategoríaDescripciónCode SecurityVulnerabilidades en tu código fuente (SAST)Open SourceVulnerabilidades en dependencias (pom.xml, build.gradle, pubspec.yaml)

📊 Interpretación de resultados
Al hacer clic en una vulnerabilidad detectada, Snyk muestra:

Nombre del issue — ej. SQL Injection, Use of Password Hash With Insufficient Computational Effort
CWE — clasificación estándar de la vulnerabilidad (ej. CWE-89, CWE-916)
Severidad — Critical / High / Medium / Low
Línea de código — ubicación exacta del problema
Data Flow — trazabilidad del flujo de datos desde el origen hasta el punto vulnerable
Fix Analysis — ejemplos de cómo otros proyectos han remediado el mismo problema
Remediación sugerida — versión parcheada de la dependencia si aplica


🎯 Severidades en Snyk
NivelÍconoDescripciónCritical🔴 CVulnerabilidad explotable de forma inmediata. Prioridad máxima.High🟠 HAlto riesgo. Debe remediarse antes de pasar a producción.Medium🟡 MRiesgo moderado. Planificar remediación.Low🔵 LRiesgo bajo. Monitorear.

📁 Estructura sugerida del repositorio
snyk-sast-guide/
├── README.md
└── screenshots/
    ├── intellij_01_marketplace.png
    ├── intellij_02_install.png
    ├── intellij_03_auth.png
    ├── intellij_04_settings.png
    ├── intellij_05_results.png
    ├── vscode_01_extensions.png
    ├── vscode_02_install.png
    ├── vscode_03_auth.png
    ├── vscode_04_settings.png
    └── vscode_05_results.png

💡 Agrega tus capturas de pantalla en la carpeta screenshots/ con los nombres indicados para que las imágenes aparezcan correctamente en el README.


📄 Licencia
Este proyecto es de uso libre con fines académicos y educativos.

<div align="center">
  Elaborado como parte del proyecto <strong>BANK — Onboarding de Crédito Banca Móvil</strong><br/>
  Flutter · Kotlin / Spring Boot · MySQL · Snyk
</div>
