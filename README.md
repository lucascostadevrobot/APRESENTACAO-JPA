# APRESENTAÇÃO JPA

Esse projeto tem como o intuito aplicar meus conhecimentos sobre JPA utilizando a Linguagem de Progamação Java.
- 
# TaskFlow

Aplicação de teste executada via terminal e com interações através do terminal.

![License](https://img.shields.io/badge/license-MIT-blue)
![Status](https://img.shields.io/badge/status-active-success)
---

:chart_with_upwards_trend:Funcionalidades

- Cadastrando Os Proprietarios e Endereços
- Lista Os Proprietarios e Endereços
- Cadastro de Proprietarios e Endereços
- Inicaliza a instancia para persistir a transação no Banco de Dados
- Faz o commit para o Banco de Dados após as transações
- Deleta Proprietarios
- Altera Proprietarios
---

:computer:Tecnologias

- Java
- JPA
- Hibernate
- MysQSL
---

:computer:Instalação
:hammer:Pré-requisitos
. Antes de começar, você precisa ter instalado:
. Java Development Kit (JDK 17 ou superior)
. Apache Maven ou Gradle
. Um banco de dados como MySQL ou PostgreSQL

:pushpin:Verifique a instalação:
```
java -version
mvn -version
======================================
````
:pushpin:Adicione ao arquivo pom.xml:

```
<dependencies>

    <!-- Hibernate ORM -->
    <dependency>
        <groupId>org.hibernate.orm</groupId>
        <artifactId>hibernate-core</artifactId>
        <version>6.4.4.Final</version>
    </dependency>

    <!-- JPA API -->
    <dependency>
        <groupId>jakarta.persistence</groupId>
        <artifactId>jakarta.persistence-api</artifactId>
        <version>3.1.0</version>
    </dependency>

    <!-- Driver MySQL -->
    <dependency>
        <groupId>com.mysql</groupId>
        <artifactId>mysql-connector-j</artifactId>
        <version>8.3.0</version>
    </dependency>

</dependencies>
````
:pushpin:Adicione ao arquivo Gradle:
```
dependencies {
    implementation 'org.hibernate.orm:hibernate-core:6.4.4.Final'
    implementation 'jakarta.persistence:jakarta.persistence-api:3.1.0'
    implementation 'com.mysql:mysql-connector-j:8.3.0'
}
````
## 7️⃣ Como usar
