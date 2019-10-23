# Configurações para rodar no JBoss

1. Acrescentar a dependência do Tomcat no pom como provided:

<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-tomcat</artifactId>
        <scope>provided</scope>
    </dependency>
</dependencies>

2. Modificar o tipo de pacote par war:

<packaging>war</packaging>

3. Modificar a super classe na classe principal de execução para extender a SpringBootServletInitializer:

@SpringBootApplication
@EnableSwagger2
public class SpringBootDemoApplication extends SpringBootServletInitializer {
  @Override
  protected SpringApplicationBuilder configure(SpringApplicationBuilder builder){
    return builder.sources(SpringBootDemoApplication.class);
  }
  public static void main(String[] args){
    SpringApplication.run(SpringBootDemoApplication.class, args);
  }
}

