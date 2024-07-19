Java class loaders are a component of the [Java virtual machine (JVM)](https://www.infoworld.com/article/3272244/what-is-the-jvm-introducing-the-java-virtual-machine.html) and are responsible for loading Java classes into memory at runtime. When a Java program is executed, one or more class loaders locate and load all the classes that are needed to run the program.

A Java class loader works by converting a class file into a Java class that can be executed by the JVM. The three primary types of class loaders in Java are as follows:

- **Bootstrap class loader**: Responsible for loading the core Java classes that are required for the JVM to function.
- **Extension class loader**: Loads classes that are part of Java extensions.
- **Application class loader**: Loads classes that are part of the application being executed. (Also known as the system class loader.)

Class loaders also are able to load classes dynamically at runtime, which allows Java programs to be more flexible and adaptable. This feature is particularly useful for applications that need to load new classes on demand, or that need to load classes from remote locations or over a network. Overall, Java class loaders are a critical component of the JVM that enables Java programs to load and execute classes dynamically at runtime.