**_api_** - used for dependencies that are exposed to external modules (transitive dependency). As the dependency is exposed to external modules, change would be a more significant re-compiling effort as everyone needs to be informed about the change

**_implementation_** used for dependencies that are internal to the component (not transitive dependency)

**_compileOnly_** used for dependencies required at compile time but never required at runtime e.g. source-only annotations. They won't be included on the runtime classpath and are non-transitive i.e. they are not exposed externally

### To see project dependency tree
`./gradlew app:dependencies` 
