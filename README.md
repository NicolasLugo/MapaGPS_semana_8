# **Mapa GPS NicolásLugo**

### **Descripción básica**
Esta es una aplicación Android que utiliza la API de Google Maps para mostrar la ubicación actual del usuario, esta aplicación muestra la ubicación exacta, es mostrada con una interfaz simple para obtener y visualizar información de ubicación en tiempo real. 

>[!Note]
>### **¿Qué hace?**
>- Muestra en tiempo real la ubicación del usuario.
>- Gestiona los permisos necesarios para que se pueda acceder a la ubicación.

>[!Important]
>### **¿Qué necesita?**
>- **API de Google Maps**: Se debe configurar una clave API en la consola de Google Cloud.
>- **Android 6.0 (API nivel 23)** o superior.
>- **Permisos de ubicación**: La aplicación solicita permisos de ubicación precisa (ACCESS_FINE_LOCATION).

>[!Tip]
>### Instalación
>1. Clona este repositorio:
>    ```bash
>    git clone https://github.com/NicolasLugo/MapaGPS_semana_8.git
>    ```
>2. Abre el proyecto en Android Studio.
>3. Agrega la clave API de Google Maps en el archivo `AndroidManifest.xml`:
>    ```xml
>    <meta-data
>        android:name="com.google.android.geo.API_KEY"
>        android:value="TU_API_KEY"/>
>    ```
>4. Ejecuta la aplicación en un emulador o dispositivo físico con Android.

>[!Tip]
>### Uso
>1. Al abrir la aplicación, se solicitarán permisos de ubicación. Concede los permisos para que la aplicación pueda obtener tu ubicación actual.
>2. Una vez concedidos los permisos, el mapa mostrará tu ubicación con un marcador.
>3. Si la ubicación no está disponible, la aplicación te notificará con un mensaje de error.

>[!Important]
>Documentación:
>- [Vulnerabilidades](app/vulnerabilities.md)
>- [Consejos de seguridad](app/security_tips.md)
>- [Buenas prácticas](app/best_practices.md)
>- [Plan de mejora futuro](app/security_improvement_program.md)
