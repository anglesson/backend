# Todo App (Backend) - React

<p align="center">
  <img src="https://img.shields.io/static/v1?label=react&message=framework&color=blue&style=for-the-badge&logo=REACT"/>
  <img src="http://img.shields.io/static/v1?label=License&message=MIT&color=green&style=for-the-badge"/>
   <img src="http://img.shields.io/static/v1?label=STATUS&message=CONCLUIDO&color=GREEN&style=for-the-badge"/>
</p>

> Status do Projeto: Concluido :heavy_check_mark:

### Tópicos
[Descrição do projeto](#descrição-do-projeto)

[Pré-requisitos](#pré-requisitos)

[Como rodar a aplicação](#como-rodar-a-aplicação)

[Schema do banco](#schema)

[Endpoints](#endpoints)

[Exemplos Requests](#exemplos-requests)

### Descrição do Projeto

<p align="justify">
   Estrutura backend da aplicação, API Rest TodoList.
</p>

### Pré Requisitos

* <a href="https://www.mongodb.com/try/download/community">Mongo</a>
* **npm** ou **yarn**


### Como rodar a aplicação

No terminal, clone o projeto:
```
git clone https://github.com/anglesson/backend.git
```

Entre na pasta do projeto:
```
cd backend
```

Instale as dependências do projeto:
```
yarn install
```

Execute a aplicação:
```
yarn dev
```
Pronto! Sua aplicação estará disponível em http://localhost:3003

### Schema

Abaixo temos a estrutura do documento TODO
``` json
{
    description: { 
        type: String, 
        required: true 
    },
    done: { 
        type: Boolean, 
        required: true, 
        default: false 
    },
    createdAt: { 
        type: Date, 
        default: Date.now 
    }
}
```
### Endpoints

`
/todos
`

### Exemplos Requests

##### Adicionar novo TODO
``` Javascript
import axios from "axios";

const options = {
  method: 'POST',
  url: 'http://localhost:3003/api/todos',
  headers: {'Content-Type': 'application/x-www-form-urlencoded'},
  data: {description: 'Limpar'}
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

##### Retorna todos TODO's
``` Javascript
import axios from "axios";

const options = {method: 'GET', url: 'http://localhost:3003/api/todos'};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

##### Atualizar TODO
``` Javascript
import axios from "axios";

const options = {
  method: 'PUT',
  url: 'http://localhost:3003/api/todos/todo_id',
  headers: {'Content-Type': 'application/x-www-form-urlencoded'},
  data: {done: 'true'}
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```
##### Excluir TODO
``` Javascript
import axios from "axios";

const options = {
  method: 'DELETE',
  url: 'http://localhost:3003/api/todos/todo_id'
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```

## Licença 

The [MIT License]() (MIT)

Copyright :copyright: 2020 - Backend TodoList - React
```