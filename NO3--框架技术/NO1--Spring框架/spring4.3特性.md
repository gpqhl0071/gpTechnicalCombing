- 隐式构造函数注入

省去了@Autowire 注解
```java
@Service
public class FooService {

    private final FooRepository repository;

    public FooService(ObjectProvider<FooRepository> repositoryProvider) {
        this.repository = repositoryProvider.getIfUnique();
    }

    public FooRepository getRepository() {
        return repository;
    }
}
```

