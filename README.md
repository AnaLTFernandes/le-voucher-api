# :ticket: Le Voucher

![Badge Finalizado](https://img.shields.io/static/v1?label=STATUS&message=FINALIZADO&color=success&style=for-the-badge)

# Índice
- [Sobre](#Sobre)
- [Rotas](#Rotas)
    - [Criar voucher](#Criar-voucher)
    - [Aplicar voucher](#Aplicar-voucher)
- [Como rodar em desenvolvimento](#Como-rodar-em-desenvolvimento)
- [Como rodar os testes](#Como-rodar-os-testes)
- [Créditos](#Créditos)

<br/>

# Sobre
Le Voucher é uma API para uma pequena loja de roupas que oferece duas rotas: uma para a criação de vouchers e outra para aplicação destes vouchers.
<br />
**Nota:** esse projeto é uma Prática de Testes Unitários.

<br/>

# Rotas

URL base: `http://localhost:5000`

<br/>

## Criar voucher
- Rota: `/vouchers`
- Método: `POST`
- Exemplo de Body:

  ```json
  {
    "code": "123Abc",
    "discount": 20
  }
  ```

<br/>

## Aplicar voucher
- Rota: `/vouchers/apply`
- Método: `POST`
- Exemplo de Body:

  ```json
  {
    "code": "123Abc",
    "amount": 100
  }
  ```
- Exemplo de Resposta:

  ```json
  {
    "amount": 100,
    "discount": 20,
    "finalAmount": 80,
    "applied": true
  }
  ```

<br/>

# Como rodar em desenvolvimento
<br/>

1. Clone esse repositório:
>```bash
> git clone https://github.com/AnaLTFernandes/le-voucher-api.git
>```

2. Na raiz do projeto, instale as dependências:
>```bash
> npm install
>```

3. Crie um banco de dados PostgreSQL com o nome que desejar

4. Configure o arquivo `.env` usando como base o arquivo `.env.example`

5. Rode as migrations para criar as tabelas no banco de dados
>```bash
> npm run prisma:migrate
>```

6. Inicie o projeto:
>```bash
> npm run dev
>```

7. Divirta-se nas rotas usando de URL base: http://localhost:{ENV_PORT}

<br/>

# Como rodar os testes
1. Siga os passos da seção [Como rodar em desenvolvimento](#Como-rodar-em-desenvolvimento)

2. Inicie os testes:
>```bash
> npm run test:unit
>```

<br/>

# Créditos
- Código base do projeto [api-le-voucher](https://github.com/Aceleracao-Testes-Unitarios-Driven/api-le-voucher) de [codethi](https://github.com/codethi)
