# HistoriasDeRequisitos

Requistos Funcionales:

Angel Cuero:

Jose Loaiza:

Angie Cobo:

Nicolas Lozano:

Santiago Ospina:

Título: Gestión de Objetos Virtuales de Aprendizaje (OVA)

Historia de Usuario:
Como administrador, quiero poder crear, editar y eliminar Objetos Virtuales de Aprendizaje (OVA), para gestionar el contenido educativo de manera eficiente.

Criterios de Aceptación:
El sistema debe mostrar un formulario para crear un nuevo OVA con campos como título, descripción y archivos multimedia.
El administrador debe poder editar los detalles de un OVA existente, incluyendo la actualización de archivos multimedia.
El administrador debe poder eliminar un OVA, lo que eliminará todos los datos asociados de la base de datos.
Cada acción (crear, editar, eliminar) debe registrar un log de auditoría para fines de seguimiento.

Alejandro Hernandez:

Requisitos No Funcionales:

Angel Cuero:

Jose Loaiza:

Angie Cobo:

Nicolas Lozano:

Santiago Ospina:
Título: Escalabilidad del Sistema

Historia de Usuario:
Como usuario, quiero que la plataforma sea escalable, para que pueda manejar un aumento en el número de usuarios sin afectar el rendimiento.

Criterios de Aceptación:
El sistema debe desplegarse en contenedores Docker y orquestarse con Kubernetes para garantizar escalabilidad horizontal.
La plataforma debe soportar hasta 10,000 usuarios concurrentes sin degradación del rendimiento.
En caso de alta demanda, el sistema debe escalar automáticamente agregando más instancias de microservicios.
El tiempo de respuesta promedio no debe exceder los 2 segundos, incluso bajo carga máxima.

Alejandro Hernandez:
