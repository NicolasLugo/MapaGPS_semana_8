# Reporte de Vulnerabilidades

## Resumen
- Vulnerabilidades encontradas: 8
- Critica: 3
- Alta: 2
- Media: 2
- Baja: 1

## 1. Permisos de localización
- **Descripción:** el acceso a distintos tipos de localización pone en riesgo la seguridad del usuario frente a eventos maliciosos.
- **Severidad:** críticos.
- **Impactos:** aplicaciones maliciosas pueden acceder a la ubicación en tiempo real, a la ubicación aproximada y a solicitar la ubicación incluso cuando la aplicación no está siendo usada, por lo que pone en riesgo la seguridad del usuario.
- **Arreglos:** se analiza la necesidad que tiene la aplicación de solicitar la ubicación en tiempo real de manera precisa y/o aproximada, así como la ubicación en segundo plano.

## 2. Certificado de depuración
- **Descripción: esta aplicación está firmada con un certificado de depuración, no con uno de producción, lo que puede generar carencias en la seguridad de la aplicación en un entorno de producción.**
- **Severidad: alta**
- **Impactos: los certificados de depuración están hechos para entornos de pruebas, por lo que son más vulnerables al ser fácilmente disponibles y no ser exclusivos.**
- **Arreglos: Android Studio tiene la herramienta de firma de APK, que permite firmar con un certificado de producción que permita la seguridad y la autenticidad de la aplicación**

## 3. Compatibilidad con versiones antiguas de Android
- **Descripción: esta aplicación es compatible con versiones no tan recientes de Android.**
- **Severidad: alta**
- **Impactos: al ser compatible con Android más antiguos, se abre la posibilidad de que hayan vulnerabilidades que ya fueron tratadas en versiones recientes pero no en versiones antiguas.**
- **Arreglos: con tal de no estar a merced de viejas vulnerabilidades, se actualiza en el build.gradle un nivel mínimo de API que sea igual o superior a 29, también se mantendrán actualizadas las librerías y las dependencias para que cualquier mejora sea aplicada en tiempo real.**

## 4. Configuración de compilación
- **Descripción:** la aplicación tiene activada la depuración en la configuración de compilación.
- **Severidad:** alta.
- **Impactos:** Con este tipo de depuración, la aplicación puede ser objeto de un ataque por parte de un ingeniero malintencionado que obtenga información delicada acerca del funcionamiento de nuestra aplicación.
- **Arreglos:** esto se arregla fácil, solo hay que cambiar esta configuración del Manifest y del build.gradle a la hora de montar la aplicación a producción.

## 5. Creación de copias de seguridad
- **Descripción: cualquier persona puede hacer respaldo de datos desde que tenga acceso al celular de la persona.**
- **Severidad:** media.
- **Impactos:** cualquier persona puede hacerse con la información almacenada en un medio físico.
- **Arreglos:** mediante un pequeño cambio en el Manifest, se impide el respaldo de datos.