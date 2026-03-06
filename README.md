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
:chart_with_upwards_trend:Configuração do JPA:

Após as configurações mencionadas acima está na hora de configurarmos o JPA, siga as etapas abaixo:
. Crie o arquivo:
````
src/main/resources/META-INF/persistence.xml
````
. Abaixo estou colocando um exemplo de configuração, mas lembre-se que essa configuração pode variar de acordo com a sua arquitetura e seu Banco de Dados.
````
<persistence xmlns="https://jakarta.ee/xml/ns/persistence"
             version="3.0">

    <persistence-unit name="jpa-example">

        <properties>

            <property name="jakarta.persistence.jdbc.url"
                      value="jdbc:mysql://localhost:3306/seubanco"/>

            <property name="jakarta.persistence.jdbc.user"
                      value="root"/>

            <property name="jakarta.persistence.jdbc.password"
                      value="senha"/>

            <property name="jakarta.persistence.jdbc.driver"
                      value="com.mysql.cj.jdbc.Driver"/>

            <property name="hibernate.dialect"
                      value="org.hibernate.dialect.MySQLDialect"/>

            <property name="hibernate.hbm2ddl.auto"
                      value="update"/>

            <property name="hibernate.show_sql"
                      value="true"/>

        </properties>

    </persistence-unit>

</persistence>
````
:chart_with_upwards_trend: Exemplo de Entidade:

O exemplo de Entidade abaixo está extensivo e complexo por fazer parte da camada de Entidades do projeto, mas fique a vontade para criar suas Entidades de acordo com sua Modelagem de Classe e UML.
<details>
<summary>🔧 Passo a passo</summary>

````
import javax.persistence.*;
import java.util.Objects;

@Entity
public class Proprietarios {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Integer id;

    @Column
    private String nome;
    @Column
    private Integer idade;
    @Column
    private boolean ativo;


    @ManyToOne(cascade=CascadeType.PERSIST)
    private EnderecoPredial enderecoPredial;

    public Proprietarios(Integer id, String nome, Integer idade, boolean ativo) {
        this.id = id;
        this.nome = nome;
        this.idade = idade;
        this.ativo = ativo;
    }

    public Proprietarios(EnderecoPredial enderecoPredial, String nome, Integer idade, boolean ativo) {
        this.enderecoPredial = enderecoPredial;
        this.nome = nome;
        this.idade = idade;
        this.ativo = ativo;
    }


    public Proprietarios() {
    }


    public EnderecoPredial getEnderecoPredial() {
        return enderecoPredial;
    }

    public void setEnderecoPredial(EnderecoPredial enderecoPredial) {
        this.enderecoPredial = enderecoPredial;
    }

    public Integer getId() {
        return id;
    }

    public void setId(Integer id) {
        this.id = id;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public Integer getIdade() {
        return idade;
    }

    public void setIdade(Integer idade) {
        this.idade = idade;
    }

    public boolean isAtivo() {
        return ativo;
    }

    public void setAtivo(boolean ativo) {
        this.ativo = ativo;
    }

    @Override
    public boolean equals(Object o) {
        if (o == null || getClass() != o.getClass()) return false;
        Proprietarios that = (Proprietarios) o;
        return ativo == that.ativo && Objects.equals(id, that.id) && Objects.equals(nome, that.nome) && Objects.equals(idade, that.idade) && Objects.equals(enderecoPredial, that.enderecoPredial);
    }

    @Override
    public int hashCode() {
        return Objects.hash(id, nome, idade, ativo, enderecoPredial);
    }

    @Override
    public String toString() {
        return "Proprietarios{" +
                "id=" + id +
                ", nome='" + nome + '\'' +
                ", idade=" + idade +
                ", ativo=" + ativo +
                ", enderecoPredial=" + enderecoPredial +
                '}';
    }
}
````
</details> ```

 
## 7️⃣ Como usar
