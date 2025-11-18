# aluguel-veiculos-Java-Web

# Sistema de Aluguel de Veículos

**Equipe 2:** Lucas Viana, Antonio Victor, Miguel Gomes, Filipe Cristiam

## 📋 Especificações Técnicas

- **IDE:** NetBeans 12.6
- **JDK:** Java 17
- **Servidor:** Apache Tomcat 9.0.19
- **Banco de Dados:** MySQL 8.0 (WampServer 3.3.7)
- **Build Tool:** Maven
- **Frameworks:** JSF 2.3 e PrimeFaces 10.0
- **Frontend:** HTML5 e CSS3

## 🚀 Funcionalidades

### CRUD Completo
- ✅ Gerenciamento de Usuários
- ✅ Gerenciamento de Veículos
- ✅ Gerenciamento de Clientes
- ✅ Gerenciamento de Aluguéis

### Funcionalidades Especiais
- ✅ Validação de disponibilidade de veículos
- ✅ Consulta de faturamento por período
- ✅ Relatório de veículos não entregues no prazo
- ✅ Interface responsiva com PrimeFaces

## 📁 Estrutura do Projeto

```
aluguel-veiculos/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/aluguel/
│   │   │       ├── model/
│   │   │       │   ├── Usuario.java
│   │   │       │   ├── Veiculo.java
│   │   │       │   ├── Cliente.java
│   │   │       │   └── Aluguel.java
│   │   │       ├── dao/
│   │   │       │   ├── UsuarioDAO.java
│   │   │       │   ├── VeiculoDAO.java
│   │   │       │   ├── ClienteDAO.java
│   │   │       │   └── AluguelDAO.java
│   │   │       ├── controller/
│   │   │       │   ├── UsuarioBean.java
│   │   │       │   ├── VeiculoBean.java
│   │   │       │   ├── ClienteBean.java
│   │   │       │   ├── AluguelBean.java
│   │   │       │   └── FaturamentoBean.java
│   │   │       └── util/
│   │   │           └── DatabaseConfig.java
│   │   ├── webapp/
│   │   │   ├── WEB-INF/
│   │   │   │   ├── web.xml
│   │   │   │   ├── faces-config.xml
│   │   │   │   └── beans.xml
│   │   │   ├── resources/
│   │   │   │   └── css/
│   │   │   │       └── styles.css
│   │   │   ├── index.xhtml
│   │   │   ├── usuario.xhtml
│   │   │   ├── veiculo.xhtml
│   │   │   ├── cliente.xhtml
│   │   │   ├── aluguel.xhtml
│   │   │   ├── faturamento.xhtml
│   │   │   └── atrasos.xhtml
├── pom.xml
└── database.sql
```

## 🔧 Instalação Passo a Passo

### 1. Pré-requisitos

Certifique-se de ter instalado:
- ✅ JDK 17
- ✅ NetBeans 12.6
- ✅ Apache Tomcat 9.0.19
- ✅ WampServer 3.3.7 (MySQL 8.0)
- ✅ Maven (geralmente incluído no NetBeans)

### 2. Configuração do Banco de Dados

1. **Inicie o WampServer** e verifique se está rodando (ícone verde)

2. **Abra o phpMyAdmin** (http://localhost/phpmyadmin)

3. **Execute o script SQL:**
   - Abra o arquivo `database.sql`
   - Copie todo o conteúdo
   - Cole na aba SQL do phpMyAdmin
   - Clique em "Executar"

4. **Verifique a criação:**
   - Banco de dados `aluguel_veiculos` deve estar criado
   - Tabelas: `usuario`, `veiculo`, `cliente`, `aluguel` devem existir
   - Dados de exemplo devem estar inseridos

### 3. Configuração da Conexão com o Banco

1. Abra o arquivo `DatabaseConfig.java`
2. Ajuste as credenciais conforme sua instalação do MySQL:

```java
private static final String URL = "jdbc:mysql://localhost:3306/aluguel_veiculos?useTimezone=true&serverTimezone=UTC&useSSL=false";
private static final String USER = "root";
private static final String PASSWORD = ""; // Coloque sua senha aqui
```

### 4. Configuração do Apache Tomcat no NetBeans

1. Abra o NetBeans 12.6
2. Vá em **Tools** → **Servers**
3. Clique em **Add Server**
4. Selecione **Apache Tomcat or TomEE**
5. Aponte para o diretório de instalação do Tomcat 9.0.19
6. Configure usuário e senha (se necessário)
7. Clique em **Finish**

### 5. Importação do Projeto no NetBeans

#### Opção A: Criar projeto novo e copiar arquivos

1. **Crie um novo projeto Maven:**
   - File → New Project
   - Maven → Web Application
   - Project Name: `aluguel-veiculos`
   - Group Id: `com.aluguel`
   - Artifact Id: `aluguel-veiculos`
   - Package: `com.aluguel`

2. **Copie os arquivos na estrutura correta:**
   - Substitua o `pom.xml` pelo fornecido
   - Copie todas as classes Java para `src/main/java/com/aluguel/`
   - Copie os arquivos XML para `src/main/webapp/WEB-INF/`
   - Copie os arquivos XHTML para `src/main/webapp/`
   - Copie o CSS para `src/main/webapp/resources/css/`

#### Opção B: Importar projeto Maven existente (se já tiver o projeto completo)

1. File → Open Project
2. Navegue até a pasta do projeto
3. Selecione o projeto e clique em **Open**

### 6. Build do Projeto

1. Clique com botão direito no projeto
2. Selecione **Clean and Build**
3. Aguarde o Maven baixar todas as dependências
4. Verifique se o build foi bem-sucedido (BUILD SUCCESS)

### 7. Deploy e Execução

1. **Configure o servidor no projeto:**
   - Clique com botão direito no projeto
   - Properties → Run
   - Server: Selecione o Tomcat 9.0.19
   - Context Path: `/aluguel-veiculos`
   - Clique em OK

2. **Execute o projeto:**
   - Clique com botão direito no projeto
   - Selecione **Run**
   - O NetBeans fará o deploy automático no Tomcat

3. **Acesse o sistema:**
   - Navegador abrirá automaticamente
   - URL: http://localhost:8080/aluguel-veiculos
   - Se não abrir, acesse manualmente a URL acima

## 🎯 Como Usar o Sistema

### Página Inicial
- Dashboard com acesso rápido a todas as funcionalidades
- Menu de navegação superior

### Gerenciar Usuários
- Cadastre usuários do sistema
- Defina nome, cargo, login, senha e e-mail

### Gerenciar Veículos
- Cadastre veículos disponíveis para aluguel
- Informe placa, fabricante, modelo, ano, portas e acessórios

### Gerenciar Clientes
- Cadastre clientes que irão alugar veículos
- Informe dados pessoais e de contato

### Gerenciar Aluguéis
- Registre novos aluguéis
- O sistema valida se o veículo está disponível
- Não permite alugar veículo já alugado e não entregue
- Marque como entregue quando o cliente devolver

### Consultar Faturamento
- Selecione um período (data início e fim)
- Sistema calcula o total faturado no período

### Aluguéis Atrasados
- Visualize veículos que não foram entregues no prazo
- Informações do cliente para contato
- Opção de marcar como entregue

## 🔒 Validações Implementadas

1. **Aluguel de Veículos:**
   - ✅ Veículo deve existir no cadastro
   - ✅ Cliente deve existir no cadastro
   - ✅ Não permite alugar veículo já alugado
   - ✅ Sistema acusa se veículo está alugado

2. **Campos Obrigatórios:**
   - ✅ Todos os campos principais são validados
   - ✅ Máscaras para CPF, telefone e valores monetários
   - ✅ Validação de e-mail

3. **Regras de Negócio:**
   - ✅ Data de entrega não pode ser anterior à data de aluguel
   - ✅ Veículo só fica disponível após marcação de entrega

## 🐛 Troubleshooting

### Erro de Conexão com Banco de Dados
- Verifique se o WampServer está rodando
- Confirme usuário e senha no `DatabaseConfig.java`
- Teste a conexão no MySQL Workbench ou phpMyAdmin

### Erro ao Compilar
- Verifique se o JDK 17 está configurado
- Execute `mvn clean install` no terminal
- Delete a pasta `target` e faça build novamente

### Erro 404 ao Acessar
- Verifique se o Tomcat está rodando
- Confirme o Context Path: `/aluguel-veiculos`
- Verifique os logs do Tomcat em `catalina.out`

### Dependências Maven não Baixam
- Verifique conexão com internet
- Delete a pasta `.m2/repository`
- Execute novamente `mvn clean install`

### JSF não Renderiza
- Verifique se as bibliotecas JSF estão no classpath
- Confirme a configuração do `web.xml`
- Limpe o cache do navegador

## 📚 Tecnologias Utilizadas

- **Java 17**: Linguagem de programação
- **JSF 2.3**: Framework web Java
- **PrimeFaces 10.0**: Biblioteca de componentes UI
- **JDBC**: Conexão com banco de dados
- **MySQL 8.0**: Sistema de gerenciamento de banco de dados
- **Maven**: Gerenciamento de dependências
- **Tomcat 9**: Servidor de aplicação
- **HTML5/CSS3**: Frontend

## 👥 Equipe

- Lucas Viana
- Antonio Victor
- Miguel Gomes
- Filipe Cristiam

## 📝 Notas Importantes

- O sistema utiliza JDBC puro (não JPA) conforme requisito
- Validação de CPF é apenas por formato (máscara)
- Dados de exemplo são inseridos automaticamente
- Sistema desenvolvido para fins acadêmicos

## 🔄 Atualizações Futuras (Sugestões)

- [ ] Sistema de login e autenticação
- [ ] Relatórios em PDF
- [ ] Dashboard com gráficos
- [ ] Sistema de multas por atraso
- [ ] Integração com API de pagamento
- [ ] Notificações por e-mail

---

**Desenvolvido com ❤️ pela Equipe 2**
