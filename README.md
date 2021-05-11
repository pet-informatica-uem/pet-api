# PET-API

API do site do PET para gestão de eventos e organização do grupo 

# Configuração
Para produção, adicione/atualize a seguinte configuração com seu host e porta

```ruby
# config/environments/production.rb
config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }
```
O código acima é o padrão para o ambiente de desenvolvimento

# Banco de dados e variáveis de ambiente
As configurações de banco estão definidas dentro do arquivo `config/database.yml`

Todas as credenciais, hosts e porta podem ser definidas por variáveis de ambiente em `config/local_env.yml`

Algumas variáveis disponíveis são:
```yml
DB_USER: database_username        # Usuário do bando de dados
DB_PASSWD: database_password      # Senha do bando de dados
JWT_SECRET_KEY: jwt_signing_key   # Chave de assinatura dos JWTs
```

## Iniciando o banco
Para iniciar o banco em modo produção certifique-se de criar o banco:
```
rails db:create
```
Depois execute as migrações
```
rails db:migrate
```
Caso as migrações falhem é recomendável usar o schema disponível com
```
rails db:schema:load
```

# Testes
Para executar os testes basta usar o comando 
```
rails test
```
Os resultados de cobertura de testes ficam armazenados no diretório `coverage/`
* Os testes, por hora, são executados no banco SQLite

# Executando a API
Para executar a API é necessário ter:
 * Ruby 3.0.1
 * Ter executado as configurações acima para o SGBD escolhido

Depois, instale as dependências do servidor com
```
bundle install
```

Com todas as configurações basta iniciar o servidor rails com

```
rails server
```

E a API estará disponível em http://localhost:3000
