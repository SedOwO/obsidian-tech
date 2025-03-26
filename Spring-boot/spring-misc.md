
## Get all Beans in a Spring app
```java
Arrays.stream(context.getBeanDefinitionNames()).forEach(System.out::println);
```

## Field Injection
```java
@Autowired
```

## Setter Injection 
```java
@Autowired  
public void setDependency1(Dependency1 dependency1) {  
    System.out.println("Setter Injection - setDependency1");  
    this.dependency1 = dependency1;  
}
```

## Constructor Injection
```java
@Autowired  
public YourBuisnessClass(Dependency1 dependency1, Dependency2 dependency2) {  
    super();  
    System.out.println("Constructor Injection - YourBuisnessClass");  
    this.dependency1 = dependency1;  
    this.dependency2 = dependency2;  
}
```
> Note:
> Constructor Injection is the best way for data injection in Spring because, everything happens in only one code block.