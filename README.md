# HistoriasDeRequisitos

## Requistos Funcionales:

### Angel Cuero:
#### Título: carga y descarga de archivos.

**Historia de Usuario:**
Como desarrollador, debo implementar una funcionalidad segura y eficiente para la carga y descarga de archivos dentro de los Objetos Virtuales de Aprendizaje (OVA), permitiendo a los usuarios gestionar contenido multimedia sin comprometer la integridad y seguridad de la plataforma.

**Criterios de Aceptación:**
-El sistema debe permitir a los usuarios autenticados cargar archivos multimedia (imágenes, videos, documentos) asociados a un OVA.

-Se debe establecer un límite configurable para el tamaño máximo de los archivos permitidos.

-Los archivos deben ser almacenados de manera segura, utilizando un servicio de almacenamiento distribuido o en la nube (ej. MinIO, AWS S3, Google Cloud Storage).

-Al descargar un archivo, el sistema debe verificar que el usuario tenga los permisos adecuados para acceder al recurso.

-Todas las descargas deben realizarse a través de enlaces firmados o autenticados para evitar accesos no autorizados.

-El sistema debe soportar la validación del tipo de archivo para prevenir la carga de contenido no permitido.

-Se debe registrar en logs cada operación de carga y descarga, incluyendo la fecha, hora, usuario y estado de la operación.

-En caso de error en la carga o descarga, el sistema debe proporcionar mensajes claros y códigos HTTP adecuados (400, 403, 404, 500).

-La implementación debe seguir buenas prácticas de seguridad, incluyendo la protección contra inyecciones de archivos maliciosos, uso de HTTPS y cifrado de datos sensibles en tránsito y en reposo.

### Jose Loaiza:

#### Título: Autenticación y Autorización.

**Historia de Usuario:** Como desarrollador, debo implementar autenticación y autorización seguras mediante OAuth2 y JWT, para garantizar que solo los usuarios autorizados puedan acceder a los recursos de la plataforma.

**Criterios de Aceptación:** El sistema debe permitir que los usuarios se autentiquen utilizando OAuth2, generando un token JWT tras un inicio de sesión exitoso. Este token debe contener información relevante del usuario, como su ID, rol y permisos. Cada solicitud a rutas protegidas debe incluir un token JWT válido, el cual será verificado para asegurar su autenticidad. Los tokens deben tener un tiempo de expiración configurable y contar con un mecanismo de refresh token para su renovación sin necesidad de un nuevo inicio de sesión. Las rutas y recursos protegidos solo deben ser accesibles según los permisos definidos en el JWT, y cualquier intento de acceso no autorizado debe ser rechazado con un código HTTP 401 o 403, según corresponda. Además, el sistema debe registrar en logs cada intento de autenticación y acceso a recursos, incluyendo la fecha, hora y resultado. Se debe permitir la revocación de tokens en caso de actividad sospechosa o a solicitud del usuario. Finalmente, la implementación debe seguir buenas prácticas de seguridad, como el almacenamiento seguro de claves, el uso de HTTPS y el cifrado de información sensible.

### Angie Cobo:

### Nicolas Lozano:

### Santiago Ospina:

#### Título: Gestión de Objetos Virtuales de Aprendizaje (OVA)

**Historia de Usuario:**
Como administrador, quiero poder crear, editar y eliminar Objetos Virtuales de Aprendizaje (OVA), para gestionar el contenido educativo de manera eficiente.

**Criterios de Aceptación:**
El sistema debe mostrar un formulario para crear un nuevo OVA con campos como título, descripción y archivos multimedia.
El administrador debe poder editar los detalles de un OVA existente, incluyendo la actualización de archivos multimedia.
El administrador debe poder eliminar un OVA, lo que eliminará todos los datos asociados de la base de datos.
Cada acción (crear, editar, eliminar) debe registrar un log de auditoría para fines de seguimiento.

### Alejandro Hernandez:

## Requisitos No Funcionales:

### Angel Cuero:

#### Título: Seguridad.

**Historia de Usuario:**
Como desarrollador, quiero garantizar la seguridad de la plataforma protegiéndola contra vulnerabilidades como inyección SQL, XSS y CSRF, asegurando la integridad y confidencialidad de los datos mediante la implementación de buenas prácticas y herramientas de seguridad.

**Criterios de Aceptación:**
-La aplicación debe contar con medidas de protección contra inyección SQL, asegurando que todas las consultas a la base de datos utilicen parámetros preparados o frameworks ORM que eviten este tipo de ataques.

-Se debe implementar un sistema de validación y sanitización de entradas para prevenir ataques de Cross-Site Scripting (XSS) y Cross-Site Request Forgery (CSRF).

-Los endpoints de la API deben utilizar HTTPS para garantizar la encriptación de los datos en tránsito.

-La plataforma debe aplicar un modelo de control de acceso basado en roles (RBAC) para restringir adecuadamente el acceso a los recursos según los permisos de cada usuario.

-Se debe integrar herramientas de análisis de seguridad estática y dinámica, como SonarQube y OWASP Dependency-Check, para detectar vulnerabilidades en el código y en las dependencias del proyecto.

-La autenticación y gestión de sesiones deben seguir buenas prácticas, utilizando OAuth2 y JWT con tiempos de expiración adecuados y un mecanismo de revocación de tokens en caso de actividad sospechosa.

-Se debe implementar monitoreo y alertas de seguridad con herramientas como Prometheus y Grafana para detectar y responder a eventos anómalos o intentos de acceso no autorizados.

-Todos los eventos de seguridad relevantes, como intentos fallidos de autenticación, cambios en permisos y accesos a datos sensibles, deben ser registrados en logs auditables con fecha, hora y detalles de la acción.

-Se debe realizar periódicamente pruebas de penetración y auditorías de seguridad para identificar y mitigar posibles vulnerabilidades antes de que puedan ser explotadas.

### Jose Loaiza:

#### Título: Mantenibilidad.

**Historia de Usuario:** Como desarrollador, quiero asegurar que el código del proyecto sea mantenible y cumpla con buenas prácticas mediante la integración de SonarQube, para facilitar la detección temprana de problemas y mejorar su calidad.

**Criterios de Aceptación:** El código del proyecto debe seguir estándares de calidad y buenas prácticas, garantizando que sea estructurado, legible y fácil de mantener. SonarQube debe estar integrado en el flujo de desarrollo para realizar análisis automáticos del código, identificando problemas como código duplicado, vulnerabilidades de seguridad, errores comunes y baja cobertura de pruebas. Los análisis deben ejecutarse en cada commit o push a la rama principal, generando reportes detallados sobre la calidad del código. Se deben definir métricas mínimas aceptables, como un umbral de deuda técnica y una cobertura de pruebas superior a un porcentaje acordado. Cualquier cambio que introduzca nuevos problemas críticos o bloquee la calidad del código debe ser corregido antes de su integración. Además, el equipo de desarrollo debe revisar periódicamente los reportes de SonarQube y aplicar mejoras continuas basadas en sus recomendaciones.

### Angie Cobo:

### Nicolas Lozano:

### Santiago Ospina:
#### Título: Escalabilidad del Sistema

**Historia de Usuario:**
Como usuario, quiero que la plataforma sea escalable, para que pueda manejar un aumento en el número de usuarios sin afectar el rendimiento.

**Criterios de Aceptación:**
El sistema debe desplegarse en contenedores Docker y orquestarse con Kubernetes para garantizar escalabilidad horizontal.
La plataforma debe soportar hasta 10,000 usuarios concurrentes sin degradación del rendimiento.
En caso de alta demanda, el sistema debe escalar automáticamente agregando más instancias de microservicios.
El tiempo de respuesta promedio no debe exceder los 2 segundos, incluso bajo carga máxima.

### Alejandro Hernandez:
