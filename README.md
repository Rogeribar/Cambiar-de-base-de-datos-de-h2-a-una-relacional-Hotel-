# Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-
Tarea
Describir Carpetas y Archivos

HotelController.java

define un controlador REST que maneja las solicitudes HTTP relacionadas con los hoteles.
![image](https://github.com/Rogeribar/Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-/assets/147789686/0a7fc952-156f-4ee8-90cd-d65e4fffa3b3)

Explicación:
@RestController: Indica que esta clase es un controlador REST.
@Autowired: Inyecta una instancia de HotelService.
@GetMapping("/hotels"): Define un endpoint HTTP GET en la ruta /hotels que devuelve una lista de hoteles al llamar al método search del servicio HotelService.

Hotel.java (Modelo)
define la entidad Hotel, que es un objeto mapeado a una tabla en la base de datos.

![image](https://github.com/Rogeribar/Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-/assets/147789686/7da69df3-b0c1-4759-982c-abe70d716fd5)

Explicación:

@Entity: Indica que esta clase es una entidad JPA.
@Id: Marca el campo hotelId como la clave primaria.
@GeneratedValue(strategy = GenerationType.IDENTITY): Especifica que hotelId es un campo autogenerado.
Define los campos hotelName y hotelAddress con sus respectivos métodos getter y setter.

HotelRepository.java
define el repositorio de Hotel, que es una interfaz que extiende JpaRepository y proporciona métodos CRUD para la entidad Hotel.

![image](https://github.com/Rogeribar/Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-/assets/147789686/f5131042-d752-4fd4-95e2-4a70eca5ea57)

Explicación:

extends JpaRepository<Hotel, Integer>: Indica que esta interfaz es un repositorio JPA para la entidad Hotel con una clave primaria de tipo Integer. Hereda métodos CRUD estándar como save, findAll, findById, deleteById, etc.


HotelsApplication.java
Este archivo es la clase principal que inicia la aplicación Spring Boot.

![image](https://github.com/Rogeribar/Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-/assets/147789686/a7008657-efab-4ad9-a3f3-62d3e3534576)

Explicación:

@SpringBootApplication: Esta anotación combina varias otras anotaciones de Spring (@Configuration, @EnableAutoConfiguration, @ComponentScan) y marca esta clase como la clase principal de configuración.
public static void main(String[] args): Este método inicia la aplicación Spring Boot llamando a SpringApplication.run.


Ejecutamos el codigo con el run
![image](https://github.com/Rogeribar/Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-/assets/147789686/afc67727-a50b-4e6f-bdc4-a23db0e23051)

Script SQL
Este script crea la tabla hotel y añade algunos registros.
![image](https://github.com/Rogeribar/Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-/assets/147789686/695e8ac1-7602-4346-a69b-e15dfd72adff)

DROP TABLE IF EXISTS hotel: Elimina la tabla hotel si ya existe.
CREATE TABLE hotel: Crea una nueva tabla hotel con columnas hotel_id, hotel_name, y hotel_address.
INSERT INTO hotel: Inserta registros en la tabla hotel.


resuktados 


![image](https://github.com/Rogeribar/Cambiar-de-base-de-datos-de-h2-a-una-relacional-Hotel-/assets/147789686/5a98e527-e636-44dc-bc3b-212290b14a8f)
