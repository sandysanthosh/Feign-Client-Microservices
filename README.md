# FeignRest-Microservices


#### Pom.xml:

```

<dependency>  
<groupId>org.springframework.cloud</groupId>    
<artifactId>spring-cloud-starter-feign</artifactId>  
<version>1.4.4.RELEASE</version>  
</dependency> 

```


#### Annotations.java:

@SpringBootApplication
@EnableFeignClients


#### SpringCloud/RestClients/CouponClient.java:

```
@FeignClient("stores")
public interface StoreClient {
    @RequestMapping(method = RequestMethod.GET, value = "/stores")
    List<Store> getStores();

    @RequestMapping(method = RequestMethod.GET, value = "/stores")
    Page<Store> getStores(Pageable pageable);

    @RequestMapping(method = RequestMethod.POST, value = "/stores/{storeId}", consumes = "application/json")
    Store update(@PathVariable("storeId") Long storeId, Store store);
}

```



#### Application.yml:

```
feign:
  client:
    config:
      default:
        connectTimeout: 5000
        readTimeout: 5000
        loggerLevel: basic
        
```

