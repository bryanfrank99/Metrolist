# Metrolist - Documentación de Análisis

## Obtención de Música
La aplicación obtiene la música principalmente de dos fuentes:

1. **YouTube Music**
   - Utiliza la API interna de YouTube Music (InnerTube)
   - Configuración del cliente:
     - `clientName = "WEB_REMIX"` (identifica la app como cliente web de YouTube Music)
     - `clientVersion` (versión del cliente, ej: "1.20250310.01.00")
   - Para actualizar la versión del cliente:
     1. Abrir DevTools en music.youtube.com
     2. Buscar solicitudes POST a `/youtubei/v1/`
     3. Encontrar el encabezado `X-YouTube-Client-Version`

2. **Kugou**
   - Utilizado principalmente para obtener letras de canciones

## Autenticación y Seguridad

### Inicio de Sesión
- Usa WebView para autenticación oficial de YouTube Music
- No almacena contraseñas
- Solo guarda localmente:
  - Cookies de sesión
  - Datos básicos de la cuenta (nombre, email)

### Seguridad
- Implementa prácticas de seguridad estándar
- Permite cerrar sesión en cualquier momento
- Incluye función para eliminar datos de cuenta
- Código abierto verificable

## Requisitos de Compilación

### Software Necesario
- Android Studio o IntelliJ IDEA
- Java Development Kit (JDK)
- Kotlin
- Android SDK

### Requisitos del Sistema
- Mínimo 4GB de RAM para compilación

### Dependencias
- Sistema de construcción: Gradle
- Repositorios:
  - Google Maven
  - Maven Central
  - JitPack

### Configuraciones Activas
- AndroidX
- Jetifier
- Configuration Cache de Gradle

### Pasos de Compilación
1. Clonar el repositorio
2. Abrir en Android Studio/IntelliJ
3. Sincronizar Gradle
4. Compilar con opción "Build" o `./gradlew assembleDebug`