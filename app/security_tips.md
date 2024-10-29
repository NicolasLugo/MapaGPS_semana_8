# Security Tips

Este documento describe consejos de seguridad implementados para reforzar la seguridad de la app.

## Consejos Implementados

- **Protección contra Inyección SQL**
  - **Descripción**: Sanitización de entradas del usuario para evitar inyecciones SQL.
  - **Beneficio**: Protege la app de ataques que intentan manipular la base de datos.

- **Autenticación y Autorización Seguras**
  - **Descripción**: Implementación de autenticación basada en token para validar usuarios.
  - **Beneficio**: Permite que solo usuarios autorizados accedan a ciertas funcionalidades.

- **Protección contra Ataques de Red (MITM)**
  - **Descripción**: Uso de HTTPS para todas las solicitudes y validación de certificados.
  - **Beneficio**: Previene que atacantes intercepten o modifiquen las comunicaciones de red.
