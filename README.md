# SNOOPY PetShop Delivery API
Situação de Aprendizagem - Back-End (Node.JS, JavaSript, VsCode, ORM Prisma, Insomnia)
## Contextualização
SNOOPY PetShop tem atuado em nossa cidade com ótimo atendimento e agilidade, é nosso cliente e necessita de um sistema Web para registro das entregas ou serviços a domicílio, como busca de animais para banho, tosa e outros serviços.<br>O P.O. após uma visita ao cliente elaborou o DER e UML DC(Diagrama de Classes) a seguir e elencou os requisitos funcionais.<br>
![DER e DC](./docs/snoopy-der-dc.png)
## Desafio
Desenvolver as funcionalidades conforme requisitos

### Requisitos funcionais
- [RF001] O sistema deve permitir o CRUD de Motoristas.
    - [RF001.1] Um motorista pode possuir mais de um telefone ou nenhum, desta forma o campo telefones deve ter espaço suficiente para cadastrar vários números (255 caracteres) e permitir nulo.
    - [RF001.2] A rota **readOne** do motorista deve mostrar os dados de um cliente específico e seus pedidos.
- [RF002] O sistema deve permitir o CRUD de pedidos.
    - [RF002.1] O sistema deve associar o pedido a um motorista.
    - [RF002.1] O Pedido deve na rota **read** deve somar o total dos **valores**.

### Casos de teste (Insomnia)
- [CT001] Deve ser cadastrado pelo menos 5 motoristas.
- [CT002] Deve ser cadastrado 1 telefone para cada motorista.
    - [CT002.1] Pelo menos 1 motorista não deve ter telefone cadastrado, ou seja **nulo**.
- [CT003] Cadastre, altere e exclua um motorista.
- [CT004] Cadastre um pedido para cada motorista.
    - [CT004.1] Pelo menos um motorista deve ter dois ou mais pedidos cadastrados.
- [CT005] Cadastre, altere e exclua um pedido.

## Tecnologias

- Node.js (Framework)
- VsCode (IDE)
- Insomnia (IDE de testes)
- Prisma (ORM)
- XAMPP (IDE)
- MySQL (SGBD) 

## Passo a Passo de como executar a API

- 1 Clone este repositório
- 2 Abrir com Vscode
- 3 Criar o arquivo **.env** na pasta API contendo:
```js
DATABASE_URL="mysql://root@localhost:3306/snoopydelivery?schema=public&timezone=UTC"
```
- Obs: certifique-se de não ter um banco de dados chamado **pizzaria** no seu MySQL.
- 4 Abrir o XAMPP e dar start em MySQL
- 5 No VsCode abra um terminal **CTRL + '** cmd ou bash e digite os seguintes comandos para baixar as dependências e instalar o Banco de dados
```bash
cd api
npm install
npm i prisma -g
npx prisma migrate dev --name init
npx nodemon
# ou
npm start
```
- 6 Abra o Insomnia e importe o arquivo **./docs/insomnia.yaml** para realizar os testes.

## Prints dos testes
![Print01](./docs/prints/Captura%201.png)
![Print02](./docs/prints/Captura%202.png)
![Print03](./docs/prints/Captura%203.png)
