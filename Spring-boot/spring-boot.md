## Spring framework
#### Terminology
- Tight Coupling and loose coupling
- IOC Container
- Application Context
- Component scan
- Dependency Injection
- Spring Beans
- Auto Wiring

## Maven
Dependency management tool

## var
```java
var marioGame = new MarioGame();

var gameRunner = new GameRunner(marioGame);

//List<String> names = List.of("Alice", "Bob", "Charlie");
var names = List.of("Alice", "Bob", "Charlie");
```


## Spring framework
Manages all the Interfaces/Dependencies 
Whatever is managed by spring is called *Spring Beans*

#### 1: Setup a config file
Make a new class with `@Configuration` annotation, which specified that, the particular class is a configuration class.

Application Context of that configuration is stored in the `context` variable as given below
```java
var context = new AnnotationConfigApplicationContext(HelloWorldConfiguration.class);
```

#### 2: Write @Beans in the @Configuration class
Refer [[java-spring#@Beans|@Beans]] for more info on beans