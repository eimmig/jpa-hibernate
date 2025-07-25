# JPA e Hibernate - Projeto Loja

Este é um projeto de estudo sobre **JPA (Java Persistence API)** e **Hibernate**, desenvolvido como exemplo de aplicação de conceitos de mapeamento objeto-relacional (ORM) em Java.

## 📋 Sobre o Projeto

O projeto simula um sistema de loja simples, demonstrando:
- Mapeamento de entidades JPA
- Relacionamentos entre entidades
- Operações CRUD com Hibernate
- Padrão DAO (Data Access Object)
- Configuração de persistence unit

## 🏗️ Arquitetura

O projeto está estruturado seguindo boas práticas de organização:

```
src/
├── main/
│   ├── java/
│   │   └── br/com/alura/loja/
│   │       ├── dao/           # Data Access Objects
│   │       ├── modelo/        # Entidades JPA
│   │       ├── testes/        # Classes de teste
│   │       └── util/          # Utilitários
│   └── resources/
│       └── META-INF/
│           └── persistence.xml # Configuração JPA
```

## 🛠️ Tecnologias Utilizadas

- **Java 11**
- **JPA (Java Persistence API)**
- **Hibernate 5.4.27.Final** - Implementação JPA
- **H2 Database** - Banco de dados em memória
- **Maven** - Gerenciamento de dependências

## 📊 Modelo de Dados

### Entidades

#### Categoria
- `id` (Long) - Chave primária
- `nome` (String) - Nome da categoria

#### Produto
- `id` (Long) - Chave primária
- `nome` (String) - Nome do produto
- `descricao` (String) - Descrição do produto
- `preco` (BigDecimal) - Preço do produto
- `dataCadastro` (LocalDate) - Data de cadastro
- `categoria` (Categoria) - Relacionamento Many-to-One

### Relacionamentos
- **Produto** ↔ **Categoria**: Relacionamento Many-to-One (muitos produtos para uma categoria)

## 🔧 Configuração

### Banco de Dados
O projeto utiliza H2 Database em memória com as seguintes configurações:
- **Driver**: `org.h2.Driver`
- **URL**: `jdbc:h2:mem:loja`
- **Usuário**: `sa`
- **Senha**: (vazia)

### Hibernate
Configurações do Hibernate no `persistence.xml`:
- **Dialeto**: H2Dialect
- **Show SQL**: true (exibe SQL no console)
- **Format SQL**: true (formata SQL no console)
- **DDL Auto**: update (atualiza schema automaticamente)

## 🚀 Como Executar

### Pré-requisitos
- Java 11 ou superior
- Maven 3.6 ou superior

### Passos
1. Clone o repositório:
```bash
git clone https://github.com/eimmig/jpa-hibernate.git
cd jpa-hibernate
```

2. Compile o projeto:
```bash
mvn clean compile
```

3. Execute a classe de teste:
```bash
mvn exec:java -Dexec.mainClass="br.com.alura.loja.testes.CadastroDeProduto"
```

## 📚 Funcionalidades Implementadas

### DAO (Data Access Object)
- **CategoriaDao**: Operações CRUD para categorias
- **ProdutoDao**: Operações CRUD para produtos com consultas customizadas

### Operações Disponíveis
- Cadastro de produtos e categorias
- Busca por ID
- Busca de produtos por nome da categoria
- Busca de preço por nome do produto
- Listagem de todos os produtos

## 🧪 Testes

O projeto inclui a classe `CadastroDeProduto` que demonstra:
- Cadastro de produtos com categorias
- Consultas utilizando o padrão DAO
- Exemplos de relacionamentos JPA

## 📖 Conceitos JPA/Hibernate Demonstrados

- **@Entity**: Mapeamento de classes como entidades
- **@Table**: Configuração de tabelas
- **@Id e @GeneratedValue**: Chaves primárias com geração automática
- **@ManyToOne**: Relacionamento muitos-para-um
- **EntityManager**: Gerenciamento de entidades
- **Persistence Unit**: Configuração de unidade de persistência
- **JPQL**: Consultas usando Java Persistence Query Language

## 🤝 Contribuindo

Este é um projeto de estudo. Sinta-se à vontade para:
- Fazer fork do projeto
- Criar branches para novas funcionalidades
- Enviar pull requests
- Reportar issues

## 📄 Licença

Este projeto é livre para uso educacional e estudo.

## 📞 Contato

Desenvolvido como projeto de estudo em JPA e Hibernate.

---

*Projeto desenvolvido para aprendizado de conceitos de persistência de dados com JPA e Hibernate.*
