# SPRING NOTES

> [!danger] COMMENT THE SPRING.SQL.INIT.MODE=ALWAYS FOR THE EXAM AFTER RUNNING 
## SET UP
### DEPENDENCIES
- Lombok
- Spring Web
- Spring Security
- H2 Database
- Validation
- Spring Data JPA
- Spring Dev Tools
### POM
```xml
<dependency>  
    <groupId>org.mapstruct</groupId>  
    <artifactId>mapstruct</artifactId>  
    <version>1.5.5.Final</version>  
</dependency>  
<dependency>  
    <groupId>org.mapstruct</groupId>  
    <artifactId>mapstruct-processor</artifactId>  
    <version>1.5.5.Final</version>  
</dependency>
<dependency>  
    <groupId>io.jsonwebtoken</groupId>  
    <artifactId>jjwt-api</artifactId>  
    <version>0.12.6</version>  
</dependency>  
<dependency>  
    <groupId>io.jsonwebtoken</groupId>  
    <artifactId>jjwt-impl</artifactId>  
    <version>0.12.6</version>  
    <scope>compile</scope>  
</dependency>  
<dependency>  
    <groupId>io.jsonwebtoken</groupId>  
    <artifactId>jjwt-jackson</artifactId>  
    <version>0.12.6</version>  
    <scope>compile</scope>  
</dependency>
<!-- https://mvnrepository.com/artifact/me.paulschwarz/spring-dotenv -->
<dependency>
    <groupId>me.paulschwarz</groupId>
    <artifactId>spring-dotenv</artifactId>
    <version>4.0.0</version>
</dependency>
<dependency> 
	<groupId>org.thymeleaf.extras</groupId> 
	<artifactId>thymeleaf-extras-springsecurity6</artifactId> 
</dependency>
```

```xml
<path>
   <groupId>org.mapstruct</groupId>
   <artifactId>mapstruct-processor</artifactId>
   <version>1.5.5.Final</version>
</path>
``` 

cuidado con lo de defer-datasource-initalization, tiene que ser true o lee primero data.sql y casca.







@JsonProperty(access = JsonProperty.Access.WRITE_ONLY) 
^--- Sólo se usa propiedad al crear un producto, no al listar.


## CONFIGURACION PERSONALIZADA 

importamos @Value de SpringFramework

https://github.com/diegokoes/DWES-03-2025-26/tree/main/EJERCICIOS  
^----- al final

@Configuration
@PropertySource...
@EnableConfigurationProperties...
Clase App config 

## SECURITY

`... implements UserDetails` - para gestionar permisos.

**Examen -> personalizar seguridad, para reglas de permisos y endopoints**

//TODO Ver ROLES DUPLICADOS 

>[!tip] @PreAuthorize y @PostAuthorize
>  Necesita @EnableMethodSecurity

>[!danger] EnableWebSecurity
> 
EnableWebSecurity no es necesario con Spring Boot 3.X / Security 6.x
## THYMELEAF

@Configuration
class en config de MvcConfig inmplements WebMvcConfigurer

registry.addViewControllers y dentro de él el mapeo de ruta y vistas 


@{/path} -> manera de resolver URL's 

siempre pasar por controller de vista a vista. Principal (autentificacion) //TODO *model* y *principal* ?? 

//TODO comunicación MVC > API REST

Par pasar de un controller a una vista, Spring proporciona Model model.  model.adAttribute.
ej. restaurants y le pasas una lista.

@Configuration
 AppConfig (en carpeta config): 
 @Value("${nombrepropiedadApplicationProperties}")

¿Web Client? -> en AppConfig (WebFlux) 

@RequiredArgsConstructor
|_ para inyectar Web Client en el **SERVICE** . 
|_ Hay 2 Beans mismo nombre? nombre diferente var.

Restaurants -> NO PAGING
Platos -> Paging

como si fuera un repository, con métodos en vez de BBDD con métodos de HTTP requests.

.get() -> .uri(sobre la base url) -> .retrieve() -> bodyToMono(clase dto) -> block()  ... 

En MVC; excepction handler devolvemos una página a la que ir.
le metemos un atributo y redireccionamos

**ETIQUETAS THYMELEAF** 

th:
...

**Utility Objects** 
no hace falta etiqueta name=""
para accedder a clases de utilidades


**MVCCONFIG SÓLO LAS PÁGINAS SIN LOGICA; ESTÁTICAS, SI HAY CONTROLLER PARA ESA RUTA, SE QUITA DEL MVC CONFIG** 

:redirect:/restaurants ... //TODO 


```xml
<dependency> <groupId>org.springframework.boot</groupId> <artifactId>spring-boot-starter-thymeleaf</artifactId> </dependency> <dependency> <groupId>org.thymeleaf.extras</groupId> <artifactId>thymeleaf-extras-springsecurity6</artifactId> </dependency> <dependency> <groupId>org.thymeleaf.extras</groupId> <artifactId>thymeleaf-extras-springsecurity6</artifactId> </dependency>
```
## SESSION

/TODO



- Seguridad de endpoints en SecurityConfig, en los endpoints o como queramos.

@ModelAttribute -> para recoger datos de una vista 
No entra reflexión en Patch

**Revisar @Builder de Entity y de DTO**

25/11 20:53 -> examen authentication, simplificar plantilla.

- **SIN MAPSTRUCK** 
Mirar lo de BindingResult 26-11
Fields, lo coge automatico al redirigir. 
- - - 
IMPORTANTE EL MODELATTRIBUTE("NAMEOFATTRIBUTE) , o llamar la variable como en thymeleaf en object. en controller en MVC

joincolumns en manytomany, da igual el nombre de la column si es en memoria, se crea con eso.

Endpoints parámetros opcionales: -> @requestparam required = false


- - - 
# SPRING 2

F5 doble submit, post redierct get, flash attributes

componentización: fragmentos (thymeleaf)

reactividad

## JPA AVANZADO


09/12 -> paginación en la API

Con ErrorDTO's enviados al MVC

WebClient -> 

ordenar dish por restaurante? 
select para numero de mostrados
- - - 
tabla intermedia con propiedades específicas ? -> crear una clase/entidad, pero no entera -> @Embeddable con esas propiedades

implements Serializable...? 

@EmbeddedId

//TODO repasar paginacion y el embedded entity. tabla intermedia?
## JPQL

query con is null , al del examen de categoria, id , estado. 
try catch controller ? 


@Query("""

SELECT o FROM Order o

WHERE (:status IS NULL OR o.status = :status)

AND (:userId IS NULL OR o.user.id = :userId)

AND (:restaurantId IS NULL OR o.restaurant.id = :restaurantId)

""")

List<Order> findByFilters(

@Param("status") String status, // no es necesario el @Param si tienen el mismo nombre

@Param("userId") Long userId,

@Param("restaurantId") Long restaurantId

);

  

@Query("""

SELECT new es.daw.foodexpressapi.dto.OrderSummaryDTO(

o.id,

u.username,

r.name,

SUM(od.quantity),

SUM(od.subtotal)

)

FROM Order o

JOIN o.user u

JOIN o.restaurant r

JOIN o.orderDetails od

GROUP BY o.id, u.username, r.name

ORDER BY o.id

""")

List<OrderSummaryDTO> findAllOrderSummaries();

- - - 
QUE NO DEBE MANTENER INFO EN LA PETICIÓN -> globalexceptionhandler
si necesito el DTO? try - catch 

JPA specifications? más avanzada //TODO

// mejora, devolver summary de un solo pedido
// pendiente usar enum para dish category. ENUMERADO COMPLEJO?  si categoria = hamburguesa -> plus precio de x euros.

// webclient -> on status PENDIENTE , con el error dto, devolver en el api el erro dto de mvc, y recogerlo con WebClient"

- - - 
### POST NAVIDAD

práctica guiada para exponer endpoints 
- swagger + hateoas
- programación orientada a aspectos
- rest repositories

Spring datarest, no saca id's  por defecto - ¿cómo se configura? 

en jpql queries, el cast para string 

enum directamente en el dto?  - > parsea json ?? llevan cadenas de texto, no enumerados !  mirar 13-01 

el JOIN FETCH **no entra** en el examen!! Todos los entities usábamos lazy. 

dto's dentro de jpql? **record**   **NO HAY RIGHT JOINS** 

spring data rest -> totalmente publico. seguridad en MVC, autenticación
sessionscope 

quizá haya que tocar al pom