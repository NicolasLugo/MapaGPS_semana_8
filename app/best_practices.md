# Best Practices

En este documento se detallan las mejores prácticas implementadas para mejorar la seguridad de la aplicación.

## Prácticas Aplicadas

- **Uso de HTTPS para Comunicación Segura**
  - **Descripción**: Todo el tráfico de red se asegura mediante HTTPS.
  - **Beneficio**: Previene ataques de tipo MiTM (Man-in-the-Middle) que podrían exponer datos sensibles.

- **Cifrado de Datos Sensibles**
  - **Descripción**: Se aplica cifrado AES para todos los datos sensibles almacenados localmente.
  - **Beneficio**: Protege la información en caso de que el dispositivo sea comprometido.

- **Deshabilitar el Modo de Depuración para Lanzamiento**
  - **Descripción**: `android:debuggable` está en `false` para el entorno de producción.
  - **Beneficio**: Impide que usuarios malintencionados depuren y extraigan información de la aplicación.

- **Validación de Entradas de Usuario**
  - **Descripción**: Todas las entradas de usuario se validan y sanitizan para prevenir inyección SQL.
  - **Beneficio**: Evita que usuarios puedan manipular consultas a la base de datos de forma maliciosa.
