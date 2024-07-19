
Java's `ClassLoader` class has the following main methods:

- `loadClass(String name)`: Loads a class with the specified name. It first checks if the class has already been loaded, and if not, it delegates the loading of the class to the parent class loader.
- `findClass(String name)`: Finds the class with the name you've specified. It is called by the `loadClass()` method if the parent class loader cannot find the class.
- `getParent()`: Returns a class loader's parent class loader.
- `getResource(String name)`: Finds the resource with the name you have specified. It searches the classpath for the resource and returns a URL object that can be used to access the resource.
- `setDefaultAssertionStatus(boolean enabled)`: Enables or disables assertions for this class loader and all classes loaded by it.