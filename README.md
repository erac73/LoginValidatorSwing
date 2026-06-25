# LoginValidatorSwing

## Descripción
LoginValidatorSwing es una aplicación de escritorio desarrollada con Java Swing que implementa un sistema de autenticación seguro para usuarios. Utiliza una base de datos MySQL gestionada a través de phpMyAdmin para almacenar las credenciales de los usuarios.

### Características principales
- **Verificación de usuario:** Comprueba si el nombre de usuario existe en la base de datos.
- **Validación de contraseña:** Verifica que la contraseña asociada al usuario sea correcta.
- **Mensajes claros:**
  - Si el usuario no existe, se muestra el mensaje: `Usuario incorrecto`.
  - Si la contraseña no coincide, se muestra el mensaje: `Contraseña incorrecta`.
  - Si ambos son correctos, se muestra un mensaje de bienvenida.

---

## Tecnologías utilizadas
- **Lenguaje de programación:** Java
- **Interfaz gráfica:** Java Swing
- **Base de datos:** MySQL
- **Herramienta de gestión de base de datos:** phpMyAdmin

---

## Requisitos
### Software necesario
- Java Development Kit (JDK) 8 o superior
- MySQL Server
- phpMyAdmin
- IDE como IntelliJ IDEA, Eclipse o NetBeans (opcional)

### Dependencias
Asegúrate de tener las bibliotecas necesarias para la conexión a la base de datos MySQL, como el conector JDBC (MySQL Connector/J).

---

## Configuración del proyecto
### 1. Configuración de la base de datos
1. Accede a phpMyAdmin.
2. Crea una base de datos llamada `login_db`.
3. Ejecuta el siguiente script SQL para crear la tabla de usuarios:

```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(255) NOT NULL
);

INSERT INTO usuarios (username, password) VALUES ('admin', '1234');
```

> **Nota:** Asegúrate de encriptar las contraseñas en un entorno de producción real.

### 2. Configuración del proyecto en Java
1. Descarga y agrega el conector JDBC (MySQL Connector/J) a tu proyecto.
2. Configura las credenciales de acceso a tu base de datos en el código Java:

```java
String url = "jdbc:mysql://localhost:3306/login_db";
String user = "root";  // Cambia esto si tu usuario es diferente
String password = "tu_contraseña";
```

---

## Uso
1. Inicia la aplicación desde tu IDE o ejecuta el archivo JAR generado.
2. Ingresa las credenciales en la interfaz gráfica:
   - Usuario: `admin`
   - Contraseña: `1234`
3. Según las credenciales ingresadas, verás uno de los siguientes mensajes:
   - `Usuario incorrecto`
   - `Contraseña incorrecta`
   - `Bienvenido`

---

## Capturas de pantalla
### Pantalla de inicio de sesión:
![image](https://github.com/user-attachments/assets/64a82d8b-607f-4774-9eae-7cee207165d8)


---

## Licencia
Este proyecto está bajo la licencia MIT. Puedes consultar el archivo `LICENSE` para más detalles.
