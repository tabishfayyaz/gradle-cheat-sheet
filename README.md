Gradle scripts are _configuration_ scripts that when executes configures an object of a particular type e.g. a build script executes and configures an object of type **_Project_**. This object is called _delegate object_ of the script.

A build script is made up of zero or more statements (method calls, assignments, variables) and _script blocks_ (e.g. allprojects{}, dependencies{}, artifacts{})

**Script Block** is a method call that takes a closure as an argument.

**Closure** is a standalone block of code which can take arguments, return values and assigned to a variable. The real value of closures is an ability to pass closure to different methods.

Gradle has two basic concepts: **projects** and **tasks**. A project can represent a library, web application or a thing to be deployed to staging/production. It is not necessarily always representing something that is built. 

**Task** represents some atomic piece of work which a build performs e.g. compiling classes, create a JAR, generate javadoc or publish some archive to a repository.

`apply plugin:` is used for plugins using an id

`apply from:` is used for plugins from a path to a local file system or a URL to a remote location. It calls the script directly as if it was part of the build file 

**_api_** - used for dependencies that are exposed to external modules (transitive dependency). As the dependency is exposed to external modules, change would be a more significant re-compiling effort as everyone needs to be informed about the change

**_implementation_** - used for dependencies that are internal to the component (not transitive dependency)

**_testImplementation_** - used for dependencies that are required to compile and run the test source of the project

**_compileOnly_** - used for dependencies required at compile time but never required at runtime e.g. source-only annotations. They won't be included on the runtime classpath and are non-transitive i.e. they are not exposed externally

**_settings.gradle_** - for settings that are build related & not necessarily project related, has access to _Gradle_ delegate object

**_gradle.properties_** - used for project wide gradle settings, allows simple key-value storage in the form of strings, automatically included in the scope of the _Project_ object

**_ext_** - used to define extra properties for _Project_ object, shorthand for `project.ext`

### To see project dependency tree
`./gradlew app:dependencies` 

### Resources

- Gradle Tutorial https://www.vogella.com/tutorials/GradleTutorial/article.html
