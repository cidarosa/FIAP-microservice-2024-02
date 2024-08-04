# MICROSERVICE AND WEB ENGINEERING
## FIAP - 2024

Material de apoio disciplina **MICROSERVICE AND WEB ENGINEERING** - FIAP - 2024/02

***

***
### Problema com dependência no Maven
#### pom.xml - Maven
No arquivo `pom.xml` – caso tenha problemas, incluir o plugin conforme código abaixo: 

```xml
<!-- Failed to execute goal org.apache.maven.plugins:maven-resources-plugin:3.2.0:resources
(default-resources) on project application-etude: Input ength = 1 -->

<plugin>
	<groupId>org.apache.maven.plugins</groupId>
	<artifactId>maven-resources-plugin</artifactId>
	<version>3.1.0</version> <!--$NO-MVN-MAN-VER$ -->
</plugin>
```

***

### Application properties
#### Ambiente de Teste - DB H2

Path: `\resources\`
File name: `application-test.properties`


```properties

# para expor o trace - somente para testes
# server.error.include-stacktrace = always
server.error.include-message=always

# para não expor o trace
server.error.include-stacktrace = never
# server.error.include-message=never

# Conexão com o banco H2
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=

# H2 Client
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# JPA, SQL
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.defer-datasource-initialization=true
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

# http://localhost:8080/h2-console/

```
***
#### Seed DB para MS-Pagamento

```sql

INSERT INTO tb_pagamento(valor, nome, numero_do_cartao, validade, codigo_de_seguranca, status, pedido_id, forma_de_pagamento_id) VALUES(1200, 'Nicodemus C Souza', '1234567890123456', '12/30', '352', 'CRIADO', 1, 2);
INSERT INTO tb_pagamento(valor, nome, numero_do_cartao, validade, codigo_de_seguranca, status, pedido_id, forma_de_pagamento_id) VALUES(500.50, 'Amadeus Mozart',  '8597452369851245', '05/28', '647', 'CRIADO', 5, 2);
INSERT INTO tb_pagamento(valor, nome, numero_do_cartao, validade, codigo_de_seguranca, status, pedido_id, forma_de_pagamento_id) VALUES(1200, 'Maria Joaquina',    '2457896547123654', '01/25', '543', 'CRIADO', 3, 2);

```







***
### Swagger e OpenAPI 3.0
#### Documentação de API e Microsserviços com Swagger e OpenAPI 3.0

##### Dependência Maven no pom.xml

```xml
<dependency>
    <groupId>org.springdoc</groupId>
    <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
    <version>2.1.0</version>
</dependency>
```

Iniciar a aplicação e acessar no navegador:
[http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html)