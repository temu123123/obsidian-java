The Application class loader (also called the system class loader) loads classes from the application's classpath. The classpath is a list of directories and JAR files that the JVM searches to find a class.

The application class loader is a standard Java class that loads classes from the directories and JAR files listed in the `CLASSPATH` environment variable or the `-classpath` command-line option. It loads the first class it finds if there are multiple versions.

The application class loader is the last class loader to search for a class. If it can't find it, the JVM throws a `ClassNotFoundException`. This class loader can also delegate class loading to its parent class loader, the extension class loader.

Aside from loading classes from the classpath, the application class loader also loads classes generated at runtime, like those created by the Java Reflection API or third-party libraries that use bytecode generation.

The application class loader is important because it lets developers easily use third-party libraries and modules in their applications.