Proyecto JPA Factura
Este proyecto implementa un sistema básico de facturación utilizando Java Persistence API (JPA). El objetivo principal es demostrar cómo gestionar entidades como Factura, Cliente, Domicilio, Articulo, Categoria, y DetalleFactura en una base de datos.

Se utiliza, Java, JPA (Java Persistence API), Hibernate (implementación de JPA), Base de datos configurada en el archivo de persistencia (persistence.xml).

El código principal en el archivo Main.java realiza las siguientes operaciones:

Configuración de la conexión: Se crea un EntityManagerFactory y un EntityManager a través de la unidad de persistencia definida como example-unit.

Transacción de base de datos:

Se inicia una transacción con entityManager.getTransaction().begin().
Se crean y persisten varias entidades relacionadas entre sí:
Factura: una factura con detalles de los artículos comprados.
Cliente: un cliente con nombre, apellido, DNI y su domicilio asociado.
Domicilio: la dirección del cliente.
Artículo: productos con denominación, cantidad y precio.
Categoria: categorías asociadas a los artículos (perecederos, lácteos, limpieza).
DetalleFactura: detalles de la factura con la cantidad comprada y el subtotal.
Las entidades son relacionadas y almacenadas en la base de datos mediante la transacción.
Persistencia de datos: Los objetos creados son persistidos en la base de datos con entityManager.persist(factura1).

Gestión de errores: Si ocurre algún error durante la transacción, esta es revertida con entityManager.getTransaction().rollback().

 Finalmente, se cierran el EntityManager y el EntityManagerFactory para liberar recursos.

Instrucciones de Ejecución
Clona el repositorio.
Asegúrate de tener una base de datos configurada y el archivo persistence.xml con los datos de conexión adecuados.
Ejecuta el método main() de la clase Main.java.
