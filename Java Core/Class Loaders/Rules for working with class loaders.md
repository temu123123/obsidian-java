There are just a few rules for working with Java class loaders. Knowing them will make your work simpler and more effective.

### Delegation

The delegation model in Java allows for loading classes flexibly and dynamically at runtime. This is useful in environments where the class loading requirements are unknown at compile-time.

For instance, in an application server, different applications may need different versions of the same class. The class loader delegation model makes it possible to meet these requirements without causing conflicts.

### Visibility

Class loaders in Java can have varying levels of visibility, which determines their ability to find and load classes from other class loaders. There are three levels of visibility:

- Parent-first visibility: The parent class loader is used first to load a class. If it cannot find the class, the child class loader is consulted. This is the default visibility model.
- Child-first visibility: The child class loader is used first to load a class. If it cannot find the class, the parent class loader is consulted. This model is useful when a different version of a class is needed.
- Hierarchical visibility: Each class loader has its own classpath, and classes loaded by a child class loader are not visible to parent class loaders. This model is useful to isolate different parts of an application from each other.

The level of visibility depends on the class loader hierarchy and the classpath, and it can have significant implications for application behavior. It's important to consider the visibility model used in an application to ensure that classes are loaded correctly and that classloading conflicts are avoided.

### Uniqueness

Java class loaders keep different versions of the same class in separate namespaces, which allows for creating multiple instances of a class with different versions. This is useful for web applications that need to load shared libraries without conflicts.

However, this feature can cause issues if not used carefully. If a class is loaded by two different class loaders, the JVM will treat them as separate classes, and objects created from them will not be interchangeable. This can lead to unexpected behavior if these objects are passed between methods expecting objects created by different class loaders.

To avoid these issues, it is recommended to use a single class loader to load classes whenever possible. When multiple class loaders are used, take extra care to ensure that objects are not passed between classes with different namespaces.