# 🎬 ScreenMatch - API REST para Gestión de Series  

En esta fase del proyecto **ScreenMatch**, desarrollamos una API REST utilizando el **Framework Spring**, con el objetivo de gestionar series y episodios. Este desarrollo incluyó la comprensión de la estructura **MVC**, el uso de **DTOs** para optimizar el intercambio de datos y la conexión entre el back-end y una aplicación front-end. También implementamos soluciones para manejar errores de **CORS**, asegurando una correcta disponibilización de datos.  

---

## 🚀 Funcionalidades Clave  

1. **Creación de una API REST**:  
   - Implementación de una API basada en el estándar REST para gestionar series y episodios.  
   - Endpoints para CRUD (Crear, Leer, Actualizar y Eliminar) de series y episodios.  

2. **Estructura MVC**:  
   - Separación lógica de responsabilidades en Modelos, Controladores y Servicios para un desarrollo más limpio y escalable.  

3. **Optimización con DTOs**:  
   - Uso de **Data Transfer Objects (DTOs)** para optimizar el intercambio de datos entre el front-end y el back-end.  

4. **Conexión con el Front-End**:  
   - Disponibilización de datos a través de la API para ser consumidos por una aplicación front-end.  

5. **Manejo de Errores de CORS**:  
   - Configuración de Spring para manejar problemas de CORS (Cross-Origin Resource Sharing), permitiendo que el front-end acceda a los datos del back-end sin restricciones.  

---

## 📂 Estructura del Proyecto  

```plaintext  
.  
├── src  
│   ├── main  
│   │   ├── java  
│   │   │   ├── com.example.screenmatch  
│   │   │   │   ├── ScreenMatchApplication.java     # Clase principal  
│   │   │   │   ├── model  
│   │   │   │   │   ├── Serie.java                 # Entidad para series  
│   │   │   │   │   ├── Episodio.java              # Entidad para episodios  
│   │   │   │   ├── repository  
│   │   │   │   │   ├── SerieRepository.java       # Repositorio para series  
│   │   │   │   │   ├── EpisodioRepository.java    # Repositorio para episodios  
│   │   │   │   ├── service  
│   │   │   │   │   ├── SerieService.java          # Lógica de negocio para series  
│   │   │   │   │   ├── EpisodioService.java       # Lógica de negocio para episodios  
│   │   │   │   ├── controller  
│   │   │   │   │   ├── SerieController.java       # Controlador REST para series  
│   │   │   │   │   ├── EpisodioController.java    # Controlador REST para episodios  
│   │   │   │   ├── dto  
│   │   │   │   │   ├── SerieDTO.java              # DTO para la entidad Serie  
│   │   │   │   │   ├── EpisodioDTO.java           # DTO para la entidad Episodio  
│   │   ├── resources  
│   │   │   ├── application.properties             # Configuración de Spring y base de datos  
│   │   │   └── cors-config.java                   # Configuración para manejo de CORS  
├── README.md                                       # Documentación del proyecto  
```  

---

## 🛠️ Tecnologías Utilizadas  

- **Lenguaje**: Java.  
- **Framework**: Spring Boot (Spring MVC y Spring Data JPA).  
- **Base de Datos**: Postgres.  
- **Front-End**: Compatible con aplicaciones front-end que consumen APIs REST (e.g., React, Angular).  
- **Seguridad**: Manejo de errores de CORS con configuración específica en Spring.  

---

## 🔧 Configuración y Ejecución  

1. **Clonar el Repositorio**:  
   ```bash  
   git clone https://github.com/tuusuario/screenmatch-api.git  
   cd screenmatch-api  
   ```  

2. **Configurar la Base de Datos**:  
   - Asegúrate de tener una base de datos Postgres en funcionamiento.  
   - Configura las credenciales en `application.properties`:  
     ```properties  
     spring.datasource.url=jdbc:postgresql://localhost:5432/screenmatch  
     spring.datasource.username=tu_usuario  
     spring.datasource.password=tu_contraseña  
     spring.jpa.hibernate.ddl-auto=update  
     ```  

3. **Ejecutar la Aplicación**:  
   - Con **Maven**, ejecuta:  
     ```bash  
     mvn spring-boot:run  
     ```  
   - La API estará disponible en `http://localhost:8080`.  

4. **Manejo de CORS**:  
   - Configuración en `CorsConfig.java`:  
     ```java  
     @Configuration  
     public class CorsConfig implements WebMvcConfigurer {  
         @Override  
         public void addCorsMappings(CorsRegistry registry) {  
             registry.addMapping("/**")  
                     .allowedOrigins("http://localhost:3000") // URL del front-end  
                     .allowedMethods("GET", "POST", "PUT", "DELETE");  
         }  
     }  
     ```  

---

## 📝 Endpoints Principales  

- **Series**:  
  - `GET /series` - Obtiene todas las series.  
  - `POST /series` - Agrega una nueva serie.  
  - `GET /series/{id}` - Obtiene una serie por ID.  
  - `DELETE /series/{id}` - Elimina una serie.  

- **Episodios**:  
  - `GET /episodios` - Obtiene todos los episodios.  
  - `POST /episodios` - Agrega un nuevo episodio.  
  - `GET /episodios/top5` - Obtiene los 5 episodios más importantes.  

---

## 🎯 Aprendizajes  

1. **Creación de APIs REST**:  
   - Comprender y estructurar APIs REST utilizando Spring Framework.  
   - Mapeo de rutas con anotaciones como `@GetMapping`, `@PostMapping`.  

2. **Estructura MVC**:  
   - Organización clara del código con Modelos, Controladores y Servicios.  

3. **DTOs y Buenas Prácticas**:  
   - Uso de **DTOs** para transferir datos entre el front-end y el back-end de manera eficiente.  

4. **Conexión Front-End y Back-End**:  
   - Configuración de CORS para permitir el acceso del front-end a los datos del back-end.  

5. **Manejo de Errores**:  
   - Soluciones para problemas comunes como errores de CORS.  

---

## 🌟 Funcionalidades Futuras  

- Implementar autenticación y autorización para proteger los endpoints.  
- Mejorar el soporte para paginación y filtrado de datos en la API.  
- Desarrollar un dashboard front-end completo para consumir los datos de la API.  

---

## 🏷️ Etiquetas  

`#Java` `#SpringBoot` `#RESTAPI` `#Postgres` `#CORS` `#MVC` `#DTOs`  
