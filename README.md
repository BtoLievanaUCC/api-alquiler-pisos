API Apartamentos

01 Descripción del proyecto

API Apartamentos es una aplicación desarrollada para gestionar información relacionada con propiedades y unidades habitacionales en alquiler. El proyecto permite administrar clientes, propiedades, unidades rentables, disponibilidades, reservas, pagos, imágenes de propiedades, reseñas y notificaciones. Incluye una API REST para realizar operaciones sobre estos recursos y una interfaz web para facilitar la administración de la información.

==========================================================================================================================

02 Tecnologías utilizadas

- Java 21: lenguaje de programación utilizado para desarrollar la aplicación.
- Spring Boot 4.1.1: framework utilizado para construir y ejecutar la aplicación.
- Spring Web MVC: permite crear los controladores y gestionar las solicitudes HTTP.
- Spring Data JPA: facilita el acceso y la administración de los datos mediante entidades y repositorios.
- MySQL: sistema de gestión de bases de datos utilizado por el proyecto.
- MySQL Connector/J: controlador utilizado para conectar Java con MySQL.
- Thymeleaf: motor de plantillas utilizado para generar las vistas HTML.
- Jakarta Bean Validation: permite validar los datos recibidos en las solicitudes.
- Spring Boot Actuator: proporciona funcionalidades de supervisión de la aplicación.
- Maven: herramienta utilizada para administrar las dependencias y construir el proyecto.

==========================================================================================================================

03 Instalación y ejecución

Requisitos previos

- Tener instalado Java JDK 21.
- Tener instalado MySQL.
- Tener acceso a una terminal para ejecutar los comandos del proyecto.
- Tener disponible el archivo pom.xml y el Maven Wrapper incluidos en el repositorio.

Pasos de instalación

1. Clonar o descargar el repositorio del proyecto.
2. Crear una base de datos en MySQL llamada apartamentos.
3. Configurar las credenciales y la dirección de conexión a la base de datos.
4. Abrir una terminal en la carpeta raíz del proyecto, donde se encuentra el archivo pom.xml.
5. Ejecutar la aplicación mediante Maven Wrapper.

En Windows, ejecutar:

mvnw.cmd spring-boot:run

En Linux o macOS, ejecutar:

./mvnw spring-boot:run

Variables de entorno necesarias

- DB_URL: dirección de conexión a la base de datos MySQL.
- DB_USERNAME: usuario de la base de datos.
- DB_PASSWORD: contraseña de la base de datos.

Para utilizar estas variables, deben configurarse en el entorno de ejecución y referenciarse en application.properties. Actualmente, el archivo de configuración del proyecto contiene los datos de conexión directamente, por lo que es necesario adaptarlo para utilizar estas variables.

Configuración de la conexión

La configuración debe apuntar a la base de datos apartamentos en MySQL. Se recomienda utilizar variables de entorno para evitar almacenar credenciales en el repositorio.

Acceso a la aplicación

La aplicación se ejecuta en el puerto 8000 por defecto.

URL local de la API:

http://localhost:8000

URL local de la interfaz web:

http://localhost:8000/

==========================================================================================================================

04 Listado de endpoints

Todos los endpoints de la API utilizan el prefijo /api.

Clientes

- GET /api/clientes - Obtener todos los clientes.
- GET /api/clientes/{id} - Obtener un cliente por su ID.
- POST /api/clientes - Registrar un nuevo cliente.
- PUT /api/clientes/{id} - Actualizar los datos de un cliente.
- DELETE /api/clientes/{id} - Eliminar un cliente.

Propiedades

- GET /api/propiedades - Obtener todas las propiedades.
- GET /api/propiedades/{id} - Obtener una propiedad por su ID.
- POST /api/propiedades - Registrar una nueva propiedad.
- PUT /api/propiedades/{id} - Actualizar una propiedad.
- DELETE /api/propiedades/{id} - Eliminar una propiedad.

Unidades rentables

- GET /api/unidades - Obtener todas las unidades rentables.
- GET /api/unidades/{id} - Obtener una unidad por su ID.
- GET /api/unidades/propiedad/{idPropiedad} - Obtener las unidades de una propiedad.
- POST /api/unidades - Registrar una nueva unidad rentable.
- PUT /api/unidades/{id} - Actualizar una unidad rentable.
- DELETE /api/unidades/{id} - Eliminar una unidad rentable.

Disponibilidades

- GET /api/disponibilidades - Obtener todas las disponibilidades.
- GET /api/disponibilidades/{id} - Obtener una disponibilidad por su ID.
- GET /api/disponibilidades/unidad/{idUnidad} - Obtener las disponibilidades de una unidad.
- POST /api/disponibilidades - Registrar una disponibilidad.
- PUT /api/disponibilidades/{id} - Actualizar una disponibilidad.
- DELETE /api/disponibilidades/{id} - Eliminar una disponibilidad.

Reservas

- GET /api/reservas - Obtener todas las reservas.
- GET /api/reservas/{id} - Obtener una reserva por su ID.
- POST /api/reservas - Registrar una nueva reserva.
- PUT /api/reservas/{id} - Actualizar una reserva.
- DELETE /api/reservas/{id} - Eliminar una reserva.

Pagos

- GET /api/pagos - Obtener todos los pagos.
- GET /api/pagos/{id} - Obtener un pago por su ID.
- GET /api/pagos/reserva/{idReserva} - Obtener los pagos asociados a una reserva.
- POST /api/pagos - Registrar un pago.
- PUT /api/pagos/{id} - Actualizar un pago.
- POST /api/pagos/{id}/confirmar - Confirmar un pago.
- POST /api/pagos/{id}/reembolsar - Reembolsar un pago.
- DELETE /api/pagos/{id} - Eliminar un pago.

Imágenes de propiedades

- GET /api/propiedad-imagenes - Obtener todas las imágenes de propiedades.
- GET /api/propiedad-imagenes/{id} - Obtener una imagen por su ID.
- GET /api/propiedad-imagenes/propiedad/{idPropiedad} - Obtener las imágenes de una propiedad.
- POST /api/propiedad-imagenes - Registrar una imagen.
- PUT /api/propiedad-imagenes/{id} - Actualizar una imagen.
- DELETE /api/propiedad-imagenes/{id} - Eliminar una imagen.

Reseñas

- GET /api/resenas - Obtener todas las reseñas.
- GET /api/resenas/{id} - Obtener una reseña por su ID.
- GET /api/resenas/reserva/{idReserva} - Obtener las reseñas asociadas a una reserva.
- POST /api/resenas - Registrar una reseña.
- PUT /api/resenas/{id} - Actualizar una reseña.
- DELETE /api/resenas/{id} - Eliminar una reseña.

Notificaciones

- GET /api/notificaciones - Obtener todas las notificaciones.
- GET /api/notificaciones/{id} - Obtener una notificación por su ID.
- GET /api/notificaciones/destinatario/{idCliente} - Obtener las notificaciones de un destinatario.
- POST /api/notificaciones - Registrar una notificación.
- PUT /api/notificaciones/{id} - Actualizar una notificación.
- DELETE /api/notificaciones/{id} - Eliminar una notificación.

Vistas web

- GET / - Mostrar el panel principal.
- GET /dashboard - Mostrar el panel principal.
- GET /clientes - Mostrar la lista de clientes.
- GET /clientes/nuevo - Mostrar el formulario para registrar un cliente.
- POST /clientes - Registrar un cliente desde el formulario.
- GET /clientes/{id}/editar - Mostrar el formulario de edición de un cliente.
- POST /clientes/{id} - Actualizar un cliente.
- POST /clientes/{id}/eliminar - Eliminar un cliente.
- GET /propiedades - Mostrar la lista de propiedades.
- GET /propiedades/nueva - Mostrar el formulario para registrar una propiedad.
- POST /propiedades - Registrar una propiedad.
- GET /propiedades/{id}/editar - Mostrar el formulario de edición de una propiedad.
- POST /propiedades/{id} - Actualizar una propiedad.
- POST /propiedades/{id}/eliminar - Eliminar una propiedad.
- GET /unidades - Mostrar la lista de unidades rentables.
- GET /propiedades/{id}/unidades - Mostrar las unidades de una propiedad.
- GET /unidades/nueva - Mostrar el formulario para registrar una unidad.
- POST /unidades - Registrar una unidad.
- GET /unidades/{id}/editar - Mostrar el formulario de edición de una unidad.
- POST /unidades/{id} - Actualizar una unidad.
- POST /unidades/{id}/eliminar - Eliminar una unidad.
- GET /reservas - Mostrar la lista de reservas.
- GET /reservas/nueva - Mostrar el formulario para registrar una reserva.
- POST /reservas - Registrar una reserva.
- GET /reservas/{id}/editar - Mostrar el formulario de edición de una reserva.
- POST /reservas/{id} - Actualizar una reserva.
- POST /reservas/{id}/cancelar - Cancelar una reserva.
- GET /pagos - Mostrar la lista de pagos.
- GET /pagos/nuevo - Mostrar el formulario para registrar un pago.
- POST /pagos - Registrar un pago.
- GET /pagos/{id}/editar - Mostrar el formulario de edición de un pago.
- POST /pagos/{id} - Actualizar un pago.
- POST /pagos/{id}/confirmar - Confirmar un pago desde la interfaz web.
- POST /pagos/{id}/reembolsar - Reembolsar un pago desde la interfaz web.
- POST /pagos/{id}/eliminar - Eliminar un pago desde la interfaz web.

