## @Beans
Annotation to specify if a method is a Bean.

```java
@Bean
public ClassName fun() {
// Function operation
}

// Rename a bean 
@Bean(name = "fun2")
public ClassName fun() {
// Function operation
}
```


## @Primary
Specifies the primary java Bean to avoid conflicts.

## @Qualifier
Specifies qualifier id, which can be called in the config file.

## @Component
- Recognizes a class a component which can be later accessed using [[#@ComponentScan]]
- An instance of class is managed by Spring framework
- here 'managed' means:
    - Spring instantiates the classes and injects any specified dependencies into them.
    - Spring injects the classes wherever needed.


## @ComponentScan
Tells where the `Components` are present
```java
@ComponentScan("package.name")
```

## Spring Container
AKA Spring context and Spring IOC(inversion of context) container
Contains all the [[#@Beans]]
1. Bean Factory
2. Application Factory

## @Lazy
Does lazy initialization instead of the default **Eager** initialization. i.e., *Lazy* initialization initializes the bean only when it is called.

>Note: NOT recommended and NOT frequently used.

## @Scope

The following annotation creates a prototype class, this creates a **new** instance every time it's called in a IOC Container.
```java
@Scope(value=ConfigurableBeanFactory.SCOPE_PROTOTYPE)
// or
@Scope(value="prototype")
```
Normally a class is **SINGLETON**, it wont be a prototype unless specified.

There are other scopes which are only applicable to **Web Applications**