<h1 align="center">
  <img alt="GoBarber" title="GoBarber" src="./gobarber.svg" width="150px" />
</h1>

---

GoBarber, uma API REST em Node.js (usando o framework Express).

---
### Libs utilizadas:

- [Node.js](https://github.com/nodejs)
- [Express](https://github.com/expressjs/express)
- [Sequelize](https://github.com/sequelize/sequelize) - ORM para manipular o banco usando **migrations**. Uma das maiores vantagens é evitar o uso de SQL e manipular o banco com Javascript. Também fornece mais flexibilidade e tratar os dados (usando *hooks*) antes de repassar ao banco.
- [Yup](https://github.com/jquense/yup) - valida os dados recebidos pelo front-end, como um campo não preenchido, aplica confirmação de senha, entre outras funcionalidades.
- [JWT](https://www.npmjs.com/package/jsonwebtoken) - autentica o administrador e bloqueia o acesso de outros usuários em rotas específicas usando um*middleware do **Express**.
- [Bcryptjs](https://www.npmjs.com/package/bcrypt) - criptografia de senhas. O banco armazena apenas o hash, não a senha em si.
- [Nodemailer](https://github.com/nodemailer/nodemailer) - serviço de envio de e-mails do **Node.js**.
- [Handlebars](https://handlebarsjs.com/) - template engine para criar os templates de email, usando HTML.
- [Bee-Queue](https://github.com/bee-queue/bee-queue) - guarda os serviços pesados em uma fila de processamento executada em segundo-plano (*background job*), tirando o trabalho do servidor.
- [Date-fns](https://github.com/date-fns/date-fns) - lidando com datas e timezone no Javascript.
- [Sentry](https://sentry.io/) - tratamento de exceções em runtime.

### Banco de Dados:

Os bancos de dados foram inicializados em containers do Docker.

- [Postgres](https://github.com/postgres/postgres) - banco relacional usado para armazenar os usuários e dados gerais que envolvem relacionamentos.
- [MongoDB](https://www.mongodb.com/) - banco NoSQL usado para armazenar as notificações. O modelo **schema-free** do Mongo permite mais flexibilidade pois não é estruturado e ganha mais performances pois não efetua *queries* nos relacionamentos.
- [Redis](https://redis.io/) - banco chave-valor usado para armazenar os background jobs. São estruturas simples contendo um identificador (chave) e os dados (valor), e não necessitam de relacionamentos. O Redis cai bem pois é simples e altamente performático.

---

## Como executar a aplicação:

Clone o repositório:
```
$ git clone https://github.com/italomarcos1/gobarber.git
```
Abra o repositório:
```
$ cd gobarber
```
Instale as libs pra rodar a aplicação (a pasta node_modules será criada):
```
$ yarn
```
Inicialize os bancos de dados (essa fase está em desenvolvimento, em breve trago instruções)

```
...
```
Abra um terminal e execute o comando abaixo para processar a fila, que roda indefinidamente capturando os *jobs* e executando em segundo plano. Deixe o terminal executando:
```
$ yarn queue
```
Finalmente, para iniciar a aplicação, rode:
```
$ yarn dev
```
## Utilizando a aplicação:

A API atua como back-end da aplicação [GoBarber Web](https://github.com/italomarcos1/gobarberweb), siga as instruções no **README** do repositório para rodar a aplicação.

Uma outra possibilidade é utilizar o [Insomnia](https://insomnia.rest/download/), um *client* para enviar as requisições e testar a API. O arquivo 'Insomnia_GoBarber' contém as requisições e rotas já prontas para testar a API no Insomnia, basta importar o workspace dentro da aplicação.

Por [Italo Marcos](https://www.linkedin.com/in/italo-m-b181b1117/)

---
## Licença

Esse projeto está sob a licença MIT. Veja o arquivo [LICENSE](https://github.com/flaviohugo14/fastfeet/blob/master/LICENSE) para mais detalhes.

---
