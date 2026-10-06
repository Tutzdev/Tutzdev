<p align="center">
  <img src="assets/header.svg" width="100%" alt="Tutz.dev: back-end developer, Java e Python">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/foco-back--end-A6FF1A?style=flat-square&labelColor=0B110B" alt="Foco: back-end">
  <img src="https://img.shields.io/badge/java-spring_boot-A6FF1A?style=flat-square&labelColor=0B110B" alt="Java e Spring Boot">
  <img src="https://img.shields.io/badge/python-flask_·_django-A6FF1A?style=flat-square&labelColor=0B110B" alt="Python, Flask e Django">
  <img src="https://img.shields.io/badge/mindset-clean_code-A6FF1A?style=flat-square&labelColor=0B110B" alt="Clean Code">
</p>

<br>

<img src="assets/sec-sobre.svg" width="100%" alt="01 // Sobre mim">

Sou desenvolvedor **back-end** e trabalho principalmente com **Java (Spring Boot)** e **Python (Flask e Django)**.

Gosto de pegar uma regra de negócio confusa e transformar em código que qualquer pessoa do time consegue **ler, testar e evoluir**. Cuido do sistema do começo ao fim: modelo os dados, desenho a API, escrevo os testes, penso na segurança e coloco em produção.

```java
public final class Tutz implements BackendDeveloper {

    @Override
    public Set<String> languages() {
        return Set.of("Java 21", "Python 3");
    }

    @Override
    public Set<String> frameworks() {
        return Set.of("Spring Boot", "Spring Security", "Spring Data JPA", "Flask", "Django");
    }

    @Override
    public List<Principle> principles() {
        return List.of(CLEAN_CODE, EFFECTIVE_JAVA, SOLID, TESTED_BUSINESS_RULES, SECURE_BY_DEFAULT);
    }

    @Override
    public String motto() {
        return "Código é lido muito mais vezes do que é escrito.";
    }
}
```

<br>

<img src="assets/sec-principios.svg" width="100%" alt="02 // Como eu escrevo código">

| Princípio | Na prática |
| --- | --- |
| **Clean Code** | Nomes que revelam intenção, métodos curtos com uma responsabilidade só, nada de número mágico. Se o código precisa de comentário pra ser entendido, eu reescrevo o código. |
| **Effective Java** | Imutabilidade por padrão (`record`, `final`, `List.copyOf`), static factories e builders, composição em vez de herança, `Optional` só em retorno, `equals`/`hashCode` coerentes e validação que falha cedo. |
| **SOLID** | Injeção por construtor, dependência de abstrações, classes coesas e baixo acoplamento entre módulos. |
| **Testes** | JUnit 5 e Mockito em cima da regra de negócio, testes de integração com banco real e cenários de erro tratados como cidadãos de primeira classe. |
| **API previsível** | REST com recursos bem nomeados, status HTTP corretos, erros padronizados com Problem Details (RFC 9457), paginação e versionamento. |
| **Segurança** | Spring Security, JWT ou sessão com CSRF, senhas com BCrypt, validação na borda, rate limiting e segredos fora do código. |
| **Dados** | Migrações versionadas com Flyway, modelagem pensada nas consultas, índices certos e zero N+1. |

<br>

<img src="assets/sec-arquitetura.svg" width="100%" alt="03 // Arquitetura">

- **Camadas com fronteiras claras:** entrada, aplicação, domínio e infraestrutura. O domínio não conhece framework.
- **Ports & Adapters** quando o domínio pede; um **monólito modular** bem organizado antes de pensar em microsserviços.
- **DTOs na borda** e mapeamento explícito: entidade nunca vaza pela API.
- **Rotinas agendadas e processamento paralelo** com controle de concorrência e reprocessamento seguro.
- **Multi-tenant** com isolamento de dados por cliente.
- **CI/CD** com GitHub Actions e deploy em VPS Linux com Nginx como proxy reverso.

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#0B110B','primaryTextColor':'#E9FFD6','primaryBorderColor':'#A6FF1A','lineColor':'#A6FF1A','clusterBkg':'#070B07','clusterBorder':'#3E5E2C','edgeLabelBackground':'#0B110B','fontFamily':'monospace'}}}%%
flowchart LR
    C([Cliente]) -->|HTTP / JSON| IN
    subgraph APP[Aplicação]
        IN[Entrada<br/>controllers · DTOs · validação]
        UC[Casos de uso<br/>orquestração · transações]
        D[Domínio<br/>entidades · regras · value objects]
        P{{Ports<br/>interfaces}}
        IN --> UC --> D
        UC --> P
    end
    OUT[Adapters de saída<br/>JPA · clients HTTP · jobs] -. implementa .-> P
    OUT --> DB[(PostgreSQL)]
```

<br>

<img src="assets/sec-stack.svg" width="100%" alt="04 // Arsenal">

<table>
  <tr>
    <td><b>Linguagens</b></td>
    <td>
      <img src="https://img.shields.io/badge/Java_21-0B110B?style=for-the-badge&logo=openjdk&logoColor=A6FF1A" alt="Java 21">
      <img src="https://img.shields.io/badge/Python-0B110B?style=for-the-badge&logo=python&logoColor=A6FF1A" alt="Python">
      <img src="https://img.shields.io/badge/SQL-0B110B?style=for-the-badge&logo=postgresql&logoColor=A6FF1A" alt="SQL">
    </td>
  </tr>
  <tr>
    <td><b>Java</b></td>
    <td>
      <img src="https://img.shields.io/badge/Spring_Boot-0B110B?style=for-the-badge&logo=springboot&logoColor=A6FF1A" alt="Spring Boot">
      <img src="https://img.shields.io/badge/Spring_Security-0B110B?style=for-the-badge&logo=springsecurity&logoColor=A6FF1A" alt="Spring Security">
      <img src="https://img.shields.io/badge/Spring_Data_JPA-0B110B?style=for-the-badge&logo=spring&logoColor=A6FF1A" alt="Spring Data JPA">
      <img src="https://img.shields.io/badge/Hibernate-0B110B?style=for-the-badge&logo=hibernate&logoColor=A6FF1A" alt="Hibernate">
      <img src="https://img.shields.io/badge/Maven-0B110B?style=for-the-badge&logo=apachemaven&logoColor=A6FF1A" alt="Maven">
    </td>
  </tr>
  <tr>
    <td><b>Python</b></td>
    <td>
      <img src="https://img.shields.io/badge/Flask-0B110B?style=for-the-badge&logo=flask&logoColor=A6FF1A" alt="Flask">
      <img src="https://img.shields.io/badge/Django-0B110B?style=for-the-badge&logo=django&logoColor=A6FF1A" alt="Django">
    </td>
  </tr>
  <tr>
    <td><b>Dados</b></td>
    <td>
      <img src="https://img.shields.io/badge/PostgreSQL-0B110B?style=for-the-badge&logo=postgresql&logoColor=A6FF1A" alt="PostgreSQL">
      <img src="https://img.shields.io/badge/Flyway-0B110B?style=for-the-badge&logo=flyway&logoColor=A6FF1A" alt="Flyway">
    </td>
  </tr>
  <tr>
    <td><b>Testes</b></td>
    <td>
      <img src="https://img.shields.io/badge/JUnit_5-0B110B?style=for-the-badge&logo=junit5&logoColor=A6FF1A" alt="JUnit 5">
      <img src="https://img.shields.io/badge/Mockito-0B110B?style=for-the-badge&logo=java&logoColor=A6FF1A" alt="Mockito">
      <img src="https://img.shields.io/badge/Pytest-0B110B?style=for-the-badge&logo=pytest&logoColor=A6FF1A" alt="Pytest">
    </td>
  </tr>
  <tr>
    <td><b>Infra</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-0B110B?style=for-the-badge&logo=docker&logoColor=A6FF1A" alt="Docker">
      <img src="https://img.shields.io/badge/GitHub_Actions-0B110B?style=for-the-badge&logo=githubactions&logoColor=A6FF1A" alt="GitHub Actions">
      <img src="https://img.shields.io/badge/Nginx-0B110B?style=for-the-badge&logo=nginx&logoColor=A6FF1A" alt="Nginx">
      <img src="https://img.shields.io/badge/Linux-0B110B?style=for-the-badge&logo=linux&logoColor=A6FF1A" alt="Linux">
      <img src="https://img.shields.io/badge/Git-0B110B?style=for-the-badge&logo=git&logoColor=A6FF1A" alt="Git">
    </td>
  </tr>
</table>

<br>

<img src="assets/sec-contato.svg" width="100%" alt="05 // Transmissão">

Quer trocar ideia sobre back-end, arquitetura ou um projeto? Me chama:

<p>
  <a href="https://github.com/Tutzdev"><img src="https://img.shields.io/badge/GitHub-Tutzdev-0B110B?style=for-the-badge&logo=github&logoColor=A6FF1A&labelColor=0B110B&color=1A2A12" alt="GitHub Tutzdev"></a>
  <!-- Coloque seu LinkedIn e e-mail aqui:
  <a href="https://www.linkedin.com/in/SEU-USUARIO"><img src="https://img.shields.io/badge/LinkedIn-0B110B?style=for-the-badge&logo=linkedin&logoColor=A6FF1A" alt="LinkedIn"></a>
  <a href="mailto:SEU@EMAIL.COM"><img src="https://img.shields.io/badge/E--mail-0B110B?style=for-the-badge&logo=gmail&logoColor=A6FF1A" alt="E-mail"></a>
  -->
</p>

> *"Make it work, make it right, make it fast."* — Kent Beck

<p align="center">
  <img src="assets/footer.svg" width="100%" alt="Fim da transmissão">
</p>
