# Projeto CodePix

## Sobre o Projeto

- É uma solução para simularmos transferência de valores entre bancos fictícios através de chaves (email, cpf...)
- Simularemos diversos bancos e contas bancárias que possuem uma chave PIX atribuída.
- Cada conta bancária poderá cadastrar suas chaves PIX
- Uma conta bancária poderá realizar transferência para outra conta em outro banco utilizando a chave PIX da conta destino
- Uma transação não pode ser perdida mesmo que: o CodePix esteja fora do ar
- Uma transação não pode ser perdida mesmo que: o banco de destino esteja fora do ar

## Sobre os Bancos

- O banco será um microsserviço com funções limitadas a cadastro de contas e chaves PIX, bem como transferência de valores.
- Utilizaremos a mesma aplicação para simular diversos bancos, mudando apenas cores, nome e código.
- Nest.js no backend (ferramenta)
- Next.js no frontend (ferramenta)

## Sobre o CodePix

- O microprocesso CodePix será responsável por intermediar as transferências bancárias
- Receberá a transação de transferência
- Encaminhará a transação para o banco de destino (status: "pending")
- Recebe a confirmação do banco de destino (status: "confirmed")
- Envia confirmação para o banco de origem informando quando o banco de destino processou
- Recebe a confirmação do banco de origem que ele processou (status: "Completed")
- Marca a transação como completa (status: "Completed")

## Cadastro e consulta de chave PIX

- Banco consulta o CodePix se a chave existe
- CodePix responde o resultado da consulta
- Banco solicita criação de chave no CodePix
- CodePix reponde com o resultado da solicitação
- Todas as chaves ficam armazenadas no CodePix
- Cada banco tem armazenado as chaves de suas próprias contas
  