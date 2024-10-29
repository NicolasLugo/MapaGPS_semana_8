# Vulnerabilities

Este documento detalla las vulnerabilidades identificadas en la aplicación Android utilizando MobSF.

## Vulnerabilidades Identificadas

- **Certificado de Depuración**  
  - **Descripción**: La aplicación está firmada con un certificado de depuración.
  - **Impacto**: Facilita la ingeniería inversa de la app en entornos de producción, aumentando el riesgo de modificaciones maliciosas.
  - **Solución**: Usar un certificado de producción para firmar la aplicación antes de su lanzamiento.

- **Modo de Depuración Habilitado**  
  - **Descripción**: La opción `android:debuggable` está habilitada.
  - **Impacto**: Permite a los atacantes enganchar depuradores y extraer información.
  - **Solución**: Deshabilitar el modo de depuración en el archivo `AndroidManifest.xml`.

- **Permisos Peligrosos de Ubicación**  
  - **Descripción**: La aplicación solicita permisos `ACCESS_FINE_LOCATION` y `ACCESS_BACKGROUND_LOCATION`.
  - **Impacto**: Malintencionados pueden utilizar estos permisos para rastrear al usuario sin su consentimiento.
  - **Solución**: Revisar la necesidad de estos permisos y limitar su uso.

- **Backup de Datos Habilitado**  
  - **Descripción**: La opción `android:allowBackup` permite hacer copias de seguridad.
  - **Impacto**: Permite a usuarios con acceso a ADB exportar datos de la app sin autenticación.
  - **Solución**: Deshabilitar `allowBackup` en el `AndroidManifest.xml`.

- **Receivers Exportados sin Protección Adecuada**  
  - **Descripción**: Un receiver de la app está expuesto sin la protección adecuada.
  - **Impacto**: Puede permitir que otras apps envíen datos maliciosos al receiver.
  - **Solución**: Agregar protección adecuada a los receivers expuestos.
