# Teste Back-end

## Desafio

O desafio é criar um sistema simples para pedir reembolsos. Esse sistema consiste em:

- listagem de reembolso
- criação de reembolso
- edição de reembolso
- exclusão de reembolso

## Pontuação

Para o teste ser considerado precisa atender aos requisitos minimos, será analisado:

- organizacao do código
- uso correto dos verbos HTTP
- boas práticas de API Rest
- SOLID
- Testes unitários (phpunit)

## Será um diferencial (não é obrigatório)

- Fazer upload de foto para evidencia dos gastos no reembolso
- Além do relatório em json, poder baixar o relatório em formato CSV
- Fazer autenticação (JWT) Sanctum / Jwt
- Aprovar o reembolso e bloquear edições posteriores do reembolso
- Relatório
- Sail (docker)

# Entrega

## Envio

Você deve enviar a documentação das requisições pelo Postman e publicar um repositório no seu Github que deve ser público e compartilhado ao final com a Sup#Pay.

## Prazo

Você tem 7 dias a partir da data que o desafio foi enviado pra você.

## Tecnologias (PHP)

    Banco de dados: MySQL / Postgres
    Linguagem: PHP
    Framework: Laravel
    Framework de teste: PHPUnit
    API: Rest
    Versionamento: Github
    Arquitetura: Queremos saber o que você conhece!

## Funcionalidades

### Cadastro de reembolso
Implementar um serviço que receba os dados do reembolso e persista no banco de dados:

```
{
  name: 'Gabriel Josefino',
  identification: '00000000000',
  jobRole: 'Não sei',
  refunds: [
    {
      date: 2019-08-12T09:33:20-03:00',
      type: 'TICKET',
      description: 'Gastei com a passagem para Porto Alegre'
      value: 108.90
    }
  ],
  createdAt : '2019-08-12T09:33:20-03:00'
}
```

### Edição de reembolso
A edicao de desconto deve permitir apenas a alteração do valor

### Listagem de reembolso
A listagem deve conter todos os dados previamente cadastrados e páginados de 10 em 10 itens por página.

### Relatório
A API deve ser capaz de através de parâmetros enviados na requisicao gerar um relatório do valor total de reembolsos por usuário e por mês.

```
{
  month: 9,
  year: 2019,
}
```

O retorno deve ser uma lista com os detalhes

- totalRefunds: soma total dos valores (value)
- refunds: quantidade total de reembolsos

```
[
     {
       month: 9,
       year: 2019,
       totalRefunds: 234.00,
       refunds: 5
       
     }
]
```