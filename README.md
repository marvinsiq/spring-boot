# spring-boot

## Criando nossa primeira aplicação com o Spring Boot

Utilizar o Spring Initializr [https://start.spring.io/](https://start.spring.io/) para criar o projeto

Incluir no pom.xml a dependência

```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

A aplicação será iniciada pelo método main da classe:

```java
package marvinsiq.com.listavip;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ListaVipApplication {

	public static void main(String[] args) {
		SpringApplication.run(ListaVipApplication.class, args);
	}

}
```

## Criando um controlador

```
package marvinsiq.com.listavip.controllers;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class ConvidadosController {

	 @RequestMapping("/")
    @ResponseBody
    public String ola(){
        return "Ola, Bem vindo ao sistema Lista VIPs";
    }
}


```

## Utilizando templates

* Incluir a dependência

```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
    <version>1.4.1.RELEASE</version>
</dependency>
```

* Criar o diretório templates dento de `src/main/resources`
* Criar a página `index.html` dentro de templates
* Adicionar arquivos estáticos (imagens, js, css...) como o bootstrap dentro do diretório `src/main/resources/static`
* Alterar o controlador para retornar para a página index

```
package marvinsiq.com.listavip.controllers;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;

@Controller
public class ConvidadosController {

	@RequestMapping("/")
	public String index() {
		return "index";
	}
}

```