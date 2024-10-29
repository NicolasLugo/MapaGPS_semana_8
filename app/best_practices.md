# Buenas Prácticas

## Resumen
- Deshabilitar permisos y funciones de depuración en producción
- Configurar el nivel mínimo de API para mantener la seguridad
- Proteger los componentes de la aplicación con permisos específicos
- Deshabilitar el respaldo de datos mediante ADB

## 1. Deshabilitar permisos y funciones de depuración en producción
**Descripción:** se asegura que la aplicación no está en modo depuración en el entorno de producción y que no incluya permisos innecesarios.
**Implementación:** en el archivo build.gradle, se establece "debuggable = false" en la configuración release para el entorno de producción. Se revisa la misma configuración en el Android.Manifest.

## 2. Configurar el nivel mínimo de API para mantener la seguridad
**Descripción:** se restringe la compatibilidad de la app a versiones de Android que reciban actualizaciones de seguridad, preferiblemente a partir de Android 10 (API 29).
**Implementación:** en el Android.manifest, se configura minSdkVersion con una versión 29 o superior para evitar la instalación en versiones conocidas con ciertas vulnerabilidades, revisando de manera periódica si hay alguna mejora disponible.

## 3. Proteger los componentes de la aplicación con permisos específicos
**Descripción:** asegura que todos los componentes tengan permisos que limiten el acceso a aplicaciones de confianza.
**Implementación:** en el android.manifest, se crea un permiso específico "android:protectionLevel='signature'" que restringe el acceso a aplicaciones firmadas solo con el mismo certificado, y usando dicho permiso en los componentes específicos, según sea requerido.

## 4. Deshabilitar permisos y funciones de depuración en producción
**Descripción:** evita que se realicen copias de seguridad mediante ADB en entornos de producción
**Implementación:** en el android.manifest, en la etiqueta de <application> se configura 'android:allowBackup="false"' para que solo los usuarios autorizados puedan hacer respaldo de sus datos.