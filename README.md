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

#### Título: Monitoreo.

**Historia de Usuario:**
Como desarrollador, quiero implementar un sistema de monitoreo con Prometheus y Grafana para visualizar el rendimiento de la plataforma en tiempo real, permitiendo la detección temprana de anomalías y la optimización del sistema.

**Criterios de Aceptación:**

-La plataforma debe contar con Prometheus para la recopilación de métricas del sistema, incluyendo uso de CPU, memoria, latencia de respuesta, tráfico de red y estado de los microservicios.

-Grafana debe estar configurado con dashboards personalizados que presenten métricas clave del sistema de forma clara y accesible.

-Se deben generar alertas automáticas en caso de detección de anomalías, como alta latencia, consumo excesivo de recursos o fallos en los servicios.

-Todas las métricas y logs deben ser almacenados y gestionados de manera eficiente, permitiendo su consulta histórica para análisis de tendencias y optimización del rendimiento.

-El monitoreo debe incluir métricas específicas de la aplicación, como número de usuarios activos, operaciones realizadas sobre los OVA y eventos de autenticación.

-La solución de monitoreo debe ser escalable, garantizando que pueda manejar el crecimiento de la plataforma sin afectar su rendimiento.

-Se deben definir umbrales de rendimiento aceptables y generar alertas cuando se superen los límites establecidos.

-El sistema de monitoreo debe integrarse con herramientas de orquestación como Kubernetes para visualizar el estado de los pods, nodos y balanceadores de carga.

-Se deben realizar revisiones periódicas de las métricas recolectadas para identificar oportunidades de mejora y ajustar configuraciones según sea necesario.

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
