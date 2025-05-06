# Ejercicios

Ejercicio 1: Clase Producto

Este ejercicio pide crear una clase con atributos privados y , con métodos getter y setter que validen que el precio sea mayor que 0.Productonombreprecio

/**
 * Clase que representa un producto con nombre y precio.
 */
public class Producto {
    // Atributos privados
    private String nombre;
    private double precio;
    
    /**
     * Constructor para crear un producto.
     * @param nombre El nombre del producto
     * @param precio El precio del producto (debe ser mayor que 0)
     */
    public Producto(String nombre, double precio) {
        this.nombre = nombre;
        // Validación en el constructor
        if (precio > 0) {
            this.precio = precio;
        } else {
            throw new IllegalArgumentException("El precio debe ser mayor que 0");
        }
    }
    
    /**
     * Obtiene el nombre del producto.
     * @return el nombre del producto
     */
    public String getNombre() {
        return nombre;
    }
    
    /**
     * Establece el nombre del producto.
     * @param nombre el nuevo nombre del producto
     */
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    
    /**
     * Obtiene el precio del producto.
     * @return el precio del producto
     */
    public double getPrecio() {
        return precio;
    }
    
    /**
     * Establece el precio del producto, asegurando que sea mayor que 0.
     * @param precio el nuevo precio del producto
     * @throws IllegalArgumentException si el precio no es mayor que 0
     */
    public void setPrecio(double precio) {
        if (precio > 0) {
            this.precio = precio;
        } else {
            throw new IllegalArgumentException("El precio debe ser mayor que 0");
        }
    }
    
    /**
     * Representación en cadena del producto.
     * @return una cadena con información del producto
     */
    @Override
    public String toString() {
        return "Producto [nombre=" + nombre + ", precio=" + precio + "]";
    }
}

Ejercicio 2: Jerarquía Vehículos
Este ejercicio requiere crear una clase base y las subclases y , sobrescribiendo el método .VehiculoAutoMotoarrancar()

/**
 * Clase base para representar un vehículo.
 */
public class Vehiculo {
    private String marca;
    private String modelo;
    private int anio;
    
    /**
     * Constructor para crear un vehículo.
     * @param marca La marca del vehículo
     * @param modelo El modelo del vehículo
     * @param anio El año de fabricación
     */
    public Vehiculo(String marca, String modelo, int anio) {
        this.marca = marca;
        this.modelo = modelo;
        this.anio = anio;
    }
    
    /**
     * Método que simula el arranque del vehículo.
     * @return un mensaje indicando que el vehículo arrancó
     */
    public String arrancar() {
        return "El vehículo está arrancando...";
    }
    
    // Getters y setters
    public String getMarca() {
        return marca;
    }
    
    public void setMarca(String marca) {
        this.marca = marca;
    }
    
    public String getModelo() {
        return modelo;
    }
    
    public void setModelo(String modelo) {
        this.modelo = modelo;
    }
    
    public int getAnio() {
        return anio;
    }
    
    public void setAnio(int anio) {
        this.anio = anio;
    }
}

/**
 * Clase que representa un automóvil, subclase de Vehículo.
 */
public class Auto extends Vehiculo {
    private int numeroPuertas;
    
    /**
     * Constructor para crear un auto.
     * @param marca La marca del auto
     * @param modelo El modelo del auto
     * @param anio El año de fabricación
     * @param numeroPuertas El número de puertas
     */
    public Auto(String marca, String modelo, int anio, int numeroPuertas) {
        super(marca, modelo, anio);
        this.numeroPuertas = numeroPuertas;
    }
    
    /**
     * Sobrescribe el método arrancar para especificar comportamiento de Auto.
     * @return un mensaje indicando que el auto arrancó
     */
    @Override
    public String arrancar() {
        return "El auto " + getMarca() + " " + getModelo() + " arranca con llave.";
    }
    
    // Getter y setter adicional
    public int getNumeroPuertas() {
        return numeroPuertas;
    }
    
    public void setNumeroPuertas(int numeroPuertas) {
        this.numeroPuertas = numeroPuertas;
    }
}

/**
 * Clase que representa una motocicleta, subclase de Vehículo.
 */
public class Moto extends Vehiculo {
    private int cilindrada;
    
    /**
     * Constructor para crear una moto.
     * @param marca La marca de la moto
     * @param modelo El modelo de la moto
     * @param anio El año de fabricación
     * @param cilindrada La cilindrada de la moto
     */
    public Moto(String marca, String modelo, int anio, int cilindrada) {
        super(marca, modelo, anio);
        this.cilindrada = cilindrada;
    }
    
    /**
     * Sobrescribe el método arrancar para especificar comportamiento de Moto.
     * @return un mensaje indicando que la moto arrancó
     */
    @Override
    public String arrancar() {
        return "La moto " + getMarca() + " " + getModelo() + " de " + cilindrada + "cc arranca con patada.";
    }
    
    // Getter y setter adicional
    public int getCilindrada() {
        return cilindrada;
    }
    
    public void setCilindrada(int cilindrada) {
        this.cilindrada = cilindrada;
    }
}

Ejercicio 3: Diagrama UML de Biblioteca
Este ejercicio solicita crear un diagrama UML para representar la relación entre , y .AutorLibroBiblioteca

classDiagram
    class Autor {
        -String nombre
        -String apellido
        -int anioNacimiento
        +Autor(String nombre, String apellido, int anioNacimiento)
        +getNombre() String
        +setNombre(String nombre) void
        +getApellido() String
        +setApellido(String apellido) void
        +getAnioNacimiento() int
        +setAnioNacimiento(int anio) void
        +getNombreCompleto() String
    }
    
    class Libro {
        -String titulo
        -String isbn
        -int anioPublicacion
        -Autor autor
        +Libro(String titulo, String isbn, int anioPublicacion, Autor autor)
        +getTitulo() String
        +setTitulo(String titulo) void
        +getIsbn() String
        +setIsbn(String isbn) void
        +getAnioPublicacion() int
        +setAnioPublicacion(int anio) void
        +getAutor() Autor
        +setAutor(Autor autor) void
        +toString() String
    }
    
    class Biblioteca {
        -String nombre
        -String direccion
        -List~Libro~ libros
        +Biblioteca(String nombre, String direccion)
        +getNombre() String
        +setNombre(String nombre) void
        +getDireccion() String
        +setDireccion(String direccion) void
        +agregarLibro(Libro libro) void
        +eliminarLibro(String isbn) boolean
        +buscarLibroPorTitulo(String titulo) List~Libro~
        +buscarLibroPorAutor(String nombreAutor) List~Libro~
        +getLibros() List~Libro~
    }
    
    Libro o-- Autor : Composición
    Biblioteca o-- Libro : Agregación

    Ejercicio 5: Principios SOLID en una App de Registro
Este ejercicio requiere rediseñar una clase monolítica aplicando los principios SOLID de Responsabilidad Única (SRP) e Interfaz Segregada (ISP).UsuarioManager
Primero mostraré cómo podría ser la clase monolítica y luego el rediseño:
Versión Original (antes del refactor)

/**
 * Clase monolítica que maneja múltiples responsabilidades.
 */
public class UsuarioManager {
    private List<Usuario> usuarios = new ArrayList<>();
    private Connection dbConnection;
    
    public UsuarioManager() {
        // Inicializa conexión a la base de datos
        try {
            this.dbConnection = DriverManager.getConnection("jdbc:mysql://localhost:3306/db", "user", "password");
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
    
    public void registrarUsuario(String nombre, String email, String password) {
        // Validar datos
        if (nombre == null || nombre.trim().isEmpty()) {
            throw new IllegalArgumentException("El nombre no puede estar vacío");
        }
        if (email == null || !email.contains("@")) {
            throw new IllegalArgumentException("Email inválido");
        }
        if (password == null || password.length() < 6) {
            throw new IllegalArgumentException("La contraseña debe tener al menos 6 caracteres");
        }
        
        // Crear usuario
        Usuario usuario = new Usuario(nombre, email, password);
        usuarios.add(usuario);
        
        // Guardar en base de datos
        try {
            PreparedStatement ps = dbConnection.prepareStatement(
                "INSERT INTO usuarios (nombre, email, password) VALUES (?, ?, ?)");
            ps.setString(1, nombre);
            ps.setString(2, email);
            ps.setString(3, password); // En la vida real, usar hashing
            ps.executeUpdate();
        } catch (SQLException e) {
            e.printStackTrace();
        }
        
        // Enviar email de bienvenida
        enviarEmailBienvenida(email, nombre);
    }
    
    private void enviarEmailBienvenida(String email, String nombre) {
        // Simulación de envío de email
        System.out.println("Enviando email a " + email);
        System.out.println("Asunto: Bienvenido a nuestra plataforma");
        System.out.println("Contenido: Hola " + nombre + ", gracias por registrarte!");
    }
    
    public List<Usuario> listarUsuarios() {
        return new ArrayList<>(usuarios);
    }
    
    public Usuario buscarPorEmail(String email) {
        return usuarios.stream()
            .filter(u -> u.getEmail().equals(email))
            .findFirst()
            .orElse(null);
    }
    
    public void eliminarUsuario(String email) {
        usuarios.removeIf(u -> u.getEmail().equals(email));
        
        // Eliminar de base de datos
        try {
            PreparedStatement ps = dbConnection.prepareStatement(
                "DELETE FROM usuarios WHERE email = ?");
            ps.setString(1, email);
            ps.executeUpdate();
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
    
    public void cerrarConexion() {
        try {
            if (dbConnection != null) {
                dbConnection.close();
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}

class Usuario {
    private String nombre;
    private String email;
    private String password;
    
    public Usuario(String nombre, String email, String password) {
        this.nombre = nombre;
        this.email = email;
        this.password = password;
    }
    
    // Getters y setters
    public String getNombre() {
        return nombre;
    }
    
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    
    public String getEmail() {
        return email;
    }
    
    public void setEmail(String email) {
        this.email = email;
    }
    
    public String getPassword() {
        return password;
    }
    
    public void setPassword(String password) {
        this.password = password;
    }
}

Versión Refactorizada aplicando SOLID

/**
 * Clase de modelo que representa un usuario.
 */
class Usuario {
    private String nombre;
    private String email;
    private String password;
    
    public Usuario(String nombre, String email, String password) {
        this.nombre = nombre;
        this.email = email;
        this.password = password;
    }
    
    // Getters y setters
    public String getNombre() {
        return nombre;
    }
    
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    
    public String getEmail() {
        return email;
    }
    
    public void setEmail(String email) {
        this.email = email;
    }
    
    public String getPassword() {
        return password;
    }
    
    public void setPassword(String password) {
        this.password = password;
    }
}

/**
 * Interfaz para validar datos de usuario (ISP)
 */
interface ValidadorUsuario {
    void validarDatosUsuario(String nombre, String email, String password);
}

/**
 * Implementación de validador de usuario
 */
class ValidadorUsuarioImpl implements ValidadorUsuario {
    @Override
    public void validarDatosUsuario(String nombre, String email, String password) {
        if (nombre == null || nombre.trim().isEmpty()) {
            throw new IllegalArgumentException("El nombre no puede estar vacío");
        }
        if (email == null || !email.contains("@")) {
            throw new IllegalArgumentException("Email inválido");
        }
        if (password == null || password.length() < 6) {
            throw new IllegalArgumentException("La contraseña debe tener al menos 6 caracteres");
        }
    }
}

/**
 * Interfaz para persistencia de usuarios (ISP)
 */
interface RepositorioUsuario {
    void guardarUsuario(Usuario usuario);
    List<Usuario> listarUsuarios();
    Usuario buscarPorEmail(String email);
    void eliminarUsuario(String email);
}

/**
 * Implementación en memoria del repositorio de usuarios
 */
class RepositorioUsuarioEnMemoria implements RepositorioUsuario {
    private List<Usuario> usuarios = new ArrayList<>();
    
    @Override
    public void guardarUsuario(Usuario usuario) {
        usuarios.add(usuario);
    }
    
    @Override
    public List<Usuario> listarUsuarios() {
        return new ArrayList<>(usuarios);
    }
    
    @Override
    public Usuario buscarPorEmail(String email) {
        return usuarios.stream()
            .filter(u -> u.getEmail().equals(email))
            .findFirst()
            .orElse(null);
    }
    
    @Override
    public void eliminarUsuario(String email) {
        usuarios.removeIf(u -> u.getEmail().equals(email));
    }
}

/**
 * Implementación de base de datos del repositorio de usuarios
 */
class RepositorioUsuarioDB implements RepositorioUsuario {
    private Connection dbConnection;
    
    public RepositorioUsuarioDB(Connection dbConnection) {
        this.dbConnection = dbConnection;
    }
    
    @Override
    public void guardarUsuario(Usuario usuario) {
        try {
            PreparedStatement ps = dbConnection.prepareStatement(
                "INSERT INTO usuarios (nombre, email, password) VALUES (?, ?, ?)");
            ps.setString(1, usuario.getNombre());
            ps.setString(2, usuario.getEmail());
            ps.setString(3, usuario.getPassword()); // En la vida real, usar hashing
            ps.executeUpdate();
        } catch (SQLException e) {
            throw new RuntimeException("Error al guardar usuario en base de datos", e);
        }
    }
    
    @Override
    public List<Usuario> listarUsuarios() {
        List<Usuario> usuarios = new ArrayList<>();
        try {
            Statement stmt = dbConnection.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT nombre, email, password FROM usuarios");
            while (rs.next()) {
                Usuario usuario = new Usuario(
                    rs.getString("nombre"),
                    rs.getString("email"),
                    rs.getString("password")
                );
                usuarios.add(usuario);
            }
        } catch (SQLException e) {
            throw new RuntimeException("Error al listar usuarios desde base de datos", e);
        }
        return usuarios;
    }
    
    @Override
    public Usuario buscarPorEmail(String email) {
        try {
            PreparedStatement ps = dbConnection.prepareStatement(
                "SELECT nombre, email, password FROM usuarios WHERE email = ?");
            ps.setString(1, email);
            ResultSet rs = ps.executeQuery();
            if (rs.next()) {
                return new Usuario(
                    rs.getString("nombre"),
                    rs.getString("email"),
                    rs.getString("password")
                );
            }
        } catch (SQLException e) {
            throw new RuntimeException("Error al buscar usuario por email", e);
        }
        return null;
    }
    
    @Override
    public void eliminarUsuario(String email) {
        try {
            PreparedStatement ps = dbConnection.prepareStatement(
                "DELETE FROM usuarios WHERE email = ?");
            ps.setString(1, email);
            ps.executeUpdate();
        } catch (SQLException e) {
            throw new RuntimeException("Error al eliminar usuario", e);
        }
    }
}

/**
 * Interfaz para servicio de notificaciones (ISP)
 */
interface ServicioNotificacion {
    void enviarMensajeBienvenida(String email, String nombre);
}

/**
 * Implementación de servicio de notificación por email
 */
class ServicioNotificacionEmail implements ServicioNotificacion {
    @Override
    public void enviarMensajeBienvenida(String email, String nombre) {
        // Simulación de envío de email
        System.out.println("Enviando email a " + email);
        System.out.println("Asunto: Bienvenido a nuestra plataforma");
        System.out.println("Contenido: Hola " + nombre + ", gracias por registrarte!");
    }
}

/**
 * Interfaz para conexión a base de datos (ISP)
 */
interface ConexionDB {
    Connection obtenerConexion();
    void cerrarConexion();
}

/**
 * Implementación de conexión a MySQL
 */
class ConexionMySQL implements ConexionDB {
    private Connection connection;
    
    @Override
    public Connection obtenerConexion() {
        try {
            if (connection == null || connection.isClosed()) {
                connection = DriverManager.getConnection(
                    "jdbc:mysql://localhost:3306/db", "user", "password");
            }
            return connection;
        } catch (SQLException e) {
            throw new RuntimeException("Error al conectar con la base de datos", e);
        }
    }
    
    @Override
    public void cerrarConexion() {
        try {
            if (connection != null && !connection.isClosed()) {
                connection.close();
            }
        } catch (SQLException e) {
            throw new RuntimeException("Error al cerrar la conexión", e);
        }
    }
}

/**
 * Clase principal que orquesta el registro de usuarios siguiendo SRP
 */
public class RegistroUsuarioService {
    private ValidadorUsuario validador;
    private RepositorioUsuario repositorio;
    private ServicioNotificacion notificador;
    
    public RegistroUsuarioService(
            ValidadorUsuario validador,
            RepositorioUsuario repositorio,
            ServicioNotificacion notificador) {
        this.validador = validador;
        this.repositorio = repositorio;
        this.notificador = notificador;
    }
    
    /**
     * Método principal para registrar un usuario.
     */
    public void registrarUsuario(String nombre, String email, String password) {
        // Validar datos
        validador.validarDatosUsuario(nombre, email, password);
        
        // Crear y guardar usuario
        Usuario usuario = new Usuario(nombre, email, password);
        repositorio.guardarUsuario(usuario);
        
        // Notificar al usuario
        notificador.enviarMensajeBienvenida(email, nombre);
    }
    
    /**
     * Obtener lista de usuarios
     */
    public List<Usuario> listarUsuarios() {
        return repositorio.listarUsuarios();
    }
    
    /**
     * Buscar usuario por email
     */
    public Usuario buscarPorEmail(String email) {
        return repositorio.buscarPorEmail(email);
    }
    
    /**
     * Eliminar usuario por email
     */
    public void eliminarUsuario(String email) {
        repositorio.eliminarUsuario(email);
    }
}

/**
 * Ejemplo de uso con inyección de dependencias
 */
class Main {
    public static void main(String[] args) {
        // Crear instancias de las dependencias
        ConexionDB conexion = new ConexionMySQL();
        ValidadorUsuario validador = new ValidadorUsuarioImpl();
        RepositorioUsuario repositorio = new RepositorioUsuarioDB(conexion.obtenerConexion());
        ServicioNotificacion notificador = new ServicioNotificacionEmail();
        
        // Inyectar dependencias al servicio principal
        RegistroUsuarioService servicio = new RegistroUsuarioService(
            validador, repositorio, notificador);
        
        // Uso del servicio
        try {
            servicio.registrarUsuario("Juan Pérez", "juan@ejemplo.com", "123456");
            System.out.println("Usuario registrado correctamente");
            
            List<Usuario> usuarios = servicio.listarUsuarios();
            System.out.println("Usuarios registrados: " + usuarios.size());
            
        } catch (Exception e) {
            System.err.println("Error: " + e.getMessage());
        } finally {
            // Cerrar conexión
            conexion.cerrarConexion();
        }
    }
}
