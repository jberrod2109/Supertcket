# Superticket
Repositorio proyecto final Jose Bertos Rodriguez grado superior administración de sistemas informáticos en red 
Resumen del Proyecto: Super Ticket
Super Ticket es una plataforma web de gestión de tickets desarrollada con el objetivo de ofrecer una solución ligera, segura y gratuita para organizaciones que necesitan gestionar incidencias, consultas o solicitudes internas. A diferencia de otras plataformas comerciales o de código abierto, Super Ticket se ha diseñado desde cero para ser multiempresa, es decir, capaz de atender múltiples organizaciones o departamentos de forma aislada, dentro de una única instancia del sistema.

Objetivo y Funcionalidad
El proyecto busca resolver una limitación común en muchas soluciones existentes: el soporte limitado o inexistente para la multitenencia. Super Ticket permite que cada empresa o cliente tenga su propio entorno lógico dentro del sistema, gracias a la implementación del campo empresa_id en las principales tablas (usuarios, tickets, respuestas). Esto garantiza que cada organización acceda únicamente a sus propios datos, sin interferencia de otras entidades.

Las funcionalidades principales incluyen:

Registro y autenticación de usuarios.

Creación y gestión de tickets clasificados por prioridad, categoría y estado.

Roles diferenciados (cliente, gestor, administrador).

Adjuntos seguros en tickets, almacenados en la nube.

Aislamiento completo entre empresas.

Interfaz adaptable para uso móvil y escritorio.

Arquitectura Técnica en la Nube (AWS)
Super Ticket se despliega íntegramente en Amazon Web Services (AWS) usando recursos gratuitos del Free Tier, y está basado en una arquitectura moderna y segura:

Contenedores Docker orquestados mediante Amazon ECS (EC2 Launch Type).

Amazon RDS (MySQL) para la base de datos relacional multiempresa.

Amazon S3 para almacenamiento de archivos adjuntos.

Amazon ACM y CloudFront para cifrado HTTPS y distribución de contenido.

IAM y Security Groups para gestión de permisos y acceso seguro.

CloudWatch para logging, métricas y monitoreo.

Toda la infraestructura se define con Terraform como infraestructura como código (IaC).

Seguridad y Escalabilidad
La seguridad se garantiza mediante:

Uso obligatorio de HTTPS (certificados de ACM o Let's Encrypt).

Variables de entorno cifradas y secretos gestionados.

Control de acceso basado en roles IAM y reglas de red (Security Groups).

Separación lógica de datos por empresa mediante filtrado SQL y validaciones.

Aunque se ejecuta en una instancia EC2 t2.micro gratuita, las pruebas demostraron que la plataforma puede manejar con eficiencia escenarios de baja concurrencia, ideal para prototipos, pymes o entornos educativos.

Conclusión
Super Ticket es una solución viable, accesible y segura para gestionar tickets en entornos distribuidos. Su arquitectura modular, su despliegue automatizado con Terraform y su capacidad para operar sin costes en AWS la convierten en una herramienta potente para organizaciones que necesiten flexibilidad, seguridad y control sin pagar licencias comerciales.

