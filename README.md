# CursoSpring2024-02-InyeccionDeDependencias 🚀

### 📋 Descripción del Proyecto
Este proyecto es parte de una práctica de clase sobre **inyección de dependencias** con Spring Boot. Desarrolla una API REST que permite listar productos y obtener detalles de un producto específico, y demuestra cómo utilizar distintas implementaciones de un repositorio de datos, desde listas predefinidas hasta archivos JSON. La **inyección de dependencias** facilita la modularidad y permite cambiar la fuente de datos sin alterar el controlador principal.

La aplicación expone una API REST que permite listar productos y obtener información detallada de un producto específico. Los datos de los productos pueden ser obtenidos desde distintas fuentes como listas predefinidas o un archivo JSON. Esto se logra gracias a la **inyección de dependencias** y el uso de **anotaciones** como `@Repository`, `@Service` y `@Autowired` que permiten modularizar el código y facilitar la gestión de las diferentes implementaciones.

### 🎯 Objetivo
El objetivo principal de esta práctica es entender cómo funciona la **inyección de dependencias** en un proyecto de Spring Boot, para facilitar el mantenimiento y la extensibilidad del código. Mediante anotaciones como `@Autowired`, `@Repository`, y `@Service`, aprendemos a separar las responsabilidades y mejorar la flexibilidad de nuestra aplicación.

En esta práctica, aprenderás a:

- Utilizar **Spring Boot** para crear controladores REST. 🌐
- Entender cómo funciona la **inyección de dependencias** en Spring. 🤖
- Trabajar con la anotación `@Primary` para definir prioridades entre diferentes implementaciones de repositorios. ⭐
- Definir y configurar beans a través de la clase `AppConfig` y el uso de `@Configuration` y `@PropertySource`. 🛠️

### 🔍 Funcionalidades
- **Listar productos**: `/api` devuelve una lista de todos los productos.
- **Mostrar producto por ID**: `/api/{id}` devuelve los detalles de un producto específico.

### 🛠️ Tecnologías utilizadas
- **Java 17**
- **Spring Boot**
- **Maven**
- **Jackson** para manejo de JSON

### ⚙️ Configuración
El bean `productJson` carga los productos desde `resources/json/product.json`. También se aplica un impuesto (`config.price.tax`) especificado en `config.properties`.

Tambien, utilizamos una propiedad (`config.price.tax`) especificada en `config.properties` para aplicar impuestos a los precios de los productos antes de retornarlos al cliente. 💸

#### Archivo `config.properties`:
```
config.price.tax=1.25d
```

### 📂 Estructura del proyecto
- `controllers` - Endpoints REST.
- `models` - Clase `Product`.
- `repositories` - Interfaces y sus implementaciones.
- `services` - Lógica de negocio.
- `AppConfig` - Configuración de beans.


5. Verifica que el archivo `resources/json/product.json` esté presente. Aquí un ejemplo del contenido:
   ```
3. Ejecuta la aplicación usando Maven:
   ```bash
   ./mvnw spring-boot:run
   ```

4. Accede a los **endpoints** REST desde tu navegador o una herramienta como Postman:
   - Listar productos: `http://localhost:8080/api`
   - Obtener un producto específico por `id`: `http://localhost:8080/api/{id}`
