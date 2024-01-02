# SolinfBroker
É um HomeBroker para fazer compras e vendas de ações das empresas cadastradas. Possui um ambiente de gestão da Empresa e de usuários. E possui uma dashboard para compra e venda de papeis.

### Casos de Uso
Para visualizar o casos de uso, precisa abrir este site: https://draw.io e importar o arquivo Diagramas1.1.drawio.


## FEATURES

 ### Administrador:

#### Usuario Admin

* Login
  * Gestão de Empresa
    * [GET POST] da empresa
    * [DELETE] da empresa (validar se não possui papeis em mercado)
    * [PUT] da empresa (desativar a empresa)
    * [GET] [GRAFICO] histórico dos Preços
    * X [PUT] add ou remover papeis
    * X [GET] [GRAFICO] Maiores Volumes
    * X Model: (valorMercado; )
  
  * Gestão de Usuário
    * [GET POST PUT DELETE] usuarios
    * [GET] Listar as ações que possui
    * [GET] Listar o Histórico de compra e venda
    * [PUT] Add dinheiro ao caixa
    * [PUT] Sacar Dinheiro do Caixa pessoal
	
### Cliente:
* Usuario
    * [PUT] Atualizar Informações Pessoais
    * [PUT] Add dinheiro ao caixa
    * [PUT] Sacar Dinheiro do Caixa pessoal
	
* DashBoard
    * [GET] Listar as ações que possui
    * [GET] Listar o Histórico de compra e venda
    * [GET] Listar as açoes do mercado
    * [POST] Criar Ordem de Venda e de Compra
    * [PUT] Cancelar Ordem Enviada
    * [GET] Listar o gráfico da são selecionada
    
* Empresa
    * [GET] Detalhar informações da empresa s
[PUT] Add dinheiro ao caixa
[PUT] Sacar Dinheiro do Caixa pessoal
DashBoard

[GET] Listar as ações que possui
[GET] Listar o Histórico de compra e venda
[GET] Listar as açoes do mercado
[POST] Criar Ordem de Venda e de Compra
[PUT] Cancelar Ordem Enviada
[GET] Listar o gráfico da são selecionada
Empresa

[GET] Detalhar informações da empresa

# Banco de Dados

## Diagramas do Banco de Dados
Os arquivos explicando cada um dos campos, tabelas e relações do banco de dados se encontram no arquivo "Diagrama do Banco.drawio" e na pasta "banco_de_dados"

O scritp corrigido do banco se encontra no arquivo "Script_criacao_BD.sql".

## Scripts do Banco de Dados
* Population.sql
  * O script de Population serve para inserir nas tableas: cliente, pessoafisica, pessoajuridica, empresa, ativo, carteira
* Population Orders.sql
  * O script serve para preencher as tabelas de ordens de compra, tanto compra como venda

## Views e Procedures
* View Cliente.sql
  * Script da view que valida se é cliente fisico ou juridico e trás o resultado da busca
* Procedure Cliente.sql
  * Script que gera uma procedure no banco que possibilita buscas por CPF, CNPJ e ID e valida se é pessoa física ou juridica no momento que faz a busca no banco de dados

### Observações

É necessário no momento da execução dos script verificar se está sendo inserido nas tabelas informações que são dependentes, por exemplo (Inserir pessoafisica e pessoajuridica antes de incluir cliente no sistema).