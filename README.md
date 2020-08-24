# FeignRest-Microservices


#### Pom.xml:

'''

<dependency>  
<groupId>org.springframework.cloud</groupId>    
<artifactId>spring-cloud-starter-feign</artifactId>  
<version>1.4.4.RELEASE</version>  
</dependency> 

'''

#### Currency.java: 

@SpringBootApplication  
@EnableFeignClients("com.javatpoint.microservices.currencyconversionservice")  
public class CurrencyConversionServiceApplication   
{  
public static void main(String[] args)   
{  
SpringApplication.run(CurrencyConversionServiceApplication.class, args);  
}  
}  
