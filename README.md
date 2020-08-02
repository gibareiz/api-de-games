# API de Games
Esta API é utilizada para testar como uma API é desenvovlida.
Essa documentação é um teste também.
## Endpoints

### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco
#### Parametros
Nenhum
#### Respostas
###### 200 - OK
Irá receber a listagem de todos os games.
Exemplo de resposta:
```
[
    {
        "id": 1,
        "title": "Batman Arkham Asylum",
        "year": 2009,
        "price": 10
    },
    {
        "id": 2,
        "title": "Batman: Arkham City",
        "year": 2011,
        "price": 20
    },
    {
        "id": 3,
        "title": "Batman: Arkham Origins",
        "year": 2013,
        "price": 30
    },
    {
        "id": 4,
        "title": "Batman: Arkham Knight",
        "year": 2015,
        "price": 40
    }
]
```
###### 401 - Falha na autenticação.
Erro ao realizar autenticação no login. Motivos: Token Inválido, Token Expirado.
```
{
    "err": "Token inválido!"
}
```

### POST /auth
Esse endpoint é responsável por realizar o login
#### Parametros
email: E-mail do usuário cadastrado no sistema
password: Senha do usuário cadastrado no sistema.

```
{
    "email":"teste@teste.com",
    "password":"123456"
}
```

#### Respostas
###### 200 - OK
Irá receber o token JWT para utilização da api.
Exemplo de resposta:
```
{
"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJnaWJhcmVpekBob3RtYWlsLmNvbSIsImlhdCI6MTU5NjM5NDgwNSwiZXhwIjoxNTk2NDM4MDA1fQ.xw2k6pGbCompRdCvrsTSOqyKKbgmBKx2ZMac_cRNP0U"
}
```

###### 401 - Falha na autenticação.
Erro ao realizar autenticação no login. Motivos: Email ou Senha incorreto.
```
{
    "err": "Token inválido!"
}
```

