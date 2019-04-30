Gradle scripts are _configuration_ scripts that when executes configures an object of a particular type e.g. a build script executes and configures an object of type **_Project_**. This object is called _delegate object_ of the script.

A build script is made up of zero or more statements (method calls, assignments, variables) and _script blocks_ (e.g. allprojects{}, dependencies{}, artifacts{})

**Script Block** is a method call that takes a closure as an argument.

**Closure** is a standalone block of code which can take arguments, return values and assigned to a variable. The real value of closures is an ability to pass closure to different methods.

Gradle has two basic concepts: **projects** and **tasks**. A project can represent a library, web application or a thing to be deployed to staging/production. It is not necessarily always representing something that is built. 

**Task** represents some atomic piece of work which a build performs e.g. compiling classes, create a JAR, generate javadoc or publish some archive to a repository.

**_api_** - used for dependencies that are exposed to external modules (transitive dependency). As the dependency is exposed to external modules, change would be a more significant re-compiling effort as everyone needs to be informed about the change

**_implementation_** used for dependencies that are internal to the component (not transitive dependency)

**_compileOnly_** used for dependencies required at compile time but never required at runtime e.g. source-only annotations. They won't be included on the runtime classpath and are non-transitive i.e. they are not exposed externally

### To see project dependency tree
`./gradlew app:dependencies` 
