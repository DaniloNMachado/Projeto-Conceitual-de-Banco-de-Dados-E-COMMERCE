# Projeto Conceitual de Banco de Dados E-COMMERCE

## Descrição do Projeto
Este projeto consiste na criação de um esquema conceitual (Schemas) para um sistema de E-commerce. O modelo é baseado em quatro (04) entidades principais, com a adição de refinamentos e melhorias nos relacionamentos entre elas, atendendo às necessidades identificadas. O objetivo é desenvolver uma estrutura clara e eficiente para gerenciar clientes, pedidos, entregas e pagamentos.


## Objetivo
Refinar o modelo inicial, acrescentando os seguintes pontos:

- Cliente Pessoa Jurídica (PJ) e Pessoa Física (PF): Uma conta pode ser PJ ou PF, mas não ambas;
- Pagamento: Possibilitar o cadastro de múltiplas formas de pagamento por pedido;
- Entrega: Inclusão de informações sobre status de entrega e código de rastreamento.

## Narrativa
Produto: 
- Os produtos são vendidos exclusivamente em uma plataforma online;
- Cada produto possui um único fornecedor;
- Um ou mais produtos podem compor um pedido.

Cliente:
- O cliente pode se cadastrar utilizando seu CPF ou CNPJ;
- O endereço do cliente determina o valor do frete;
- Um cliente pode realizar múltiplos pedidos e possui um período de carência para devolução.

Pedido:
- Os pedidos são criados pelos clientes, contendo informações sobre compra, endereço e status de entrega;
- Um pedido pode incluir um ou mais produtos;
- Os pedidos podem ser cancelados.

Entrega:
- Cada pedido possui um status de entrega (pendente, em trânsito, entregue) e um código de rastreamento.

# Implementações Técnicas

## 1. Diferenciação de Clientes:
- Adição do atributo `Tipo de Cliente` na tabela `Clientes`, categorizando-os como PF ou PJ.
- Uso de restrições para garantir que uma conta seja exclusivamente de um dos tipos.

## 2. Forma de Pagamento:
- Criação de uma tabela "FormaPagamento" para permitir múltiplas opções associadas a um único pedido.

## 3. Entrega:
- Adição dos atributos `Status de Entrega` e `Código de Rastreamento` para gerenciar informações logísticas.

## 4. Frete Baseado no Endereço:
- Implementação de uma tabela `Frete por Região` para armazenar valores de frete por região.
- Relação entre a tabela `Clientes` e `Frete por Região` para determinar o valor do frete no momento da criação do pedido.

## 5. Cancelamento de Pedido:
- Inclusão de um campo `Status do Pedido` na tabela `Pedidos`, usando ENUM com valores como "Pendente", "Em Andamento", "Entregue" e "Cancelado". Incluso a opção de pendente como default.

## Ferramentas utilizadas
MySQL Workbench 8.0 CE

# Imagem do Projeto
![Projeto conceitual de Banco de Dados - GIT](https://github.com/user-attachments/assets/1b9b7bbe-f6d6-43fe-b27d-40abc2c18b90)
