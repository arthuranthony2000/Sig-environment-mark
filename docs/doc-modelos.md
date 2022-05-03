# Documento de Modelos

Neste documento foi utilizado o modelo de dados Entidade-Relacionamento, descrevendo também as entidades e finalizando com o dicionário de dados.

## Modelo de Dados (Entidade-Relacionamento) 

## Descrição das Entidades

Abaixo temos uma breve descrição das entidades que compõe o sistema.

| Entidade | Descrição   |
|----------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ambiente   | A entidade Ambiente possui diversos atributos, dentre eles temos os atributos de dataModificacao, dataReservaInic e dataReservaFim, para definir a data de reserva incial e final e a data que possa existir alguma mudança cadastral, existe também o atributo de tipo e capacidade, onde é definido o tipo de ambiente e sua capacidade que são caracteristicas dos ambientes, assim como participante que define por FK o codigo do usuario que está reservando o ambiente.                                |
| Usuário   | A entidade usuário é usada para armazenar os dados pessoais e gerenciar permissões de reserva e contatos.                                                              |

## Dicionário de Dados

O dicionário de dados consiste em um conjunto de tabelas que fornecem informações sobre outras tabelas no banco de dados. Dessa forma, o dicionário de dados configura-se como um repositório de metadados, armazenado em um banco de dados relacional, descrevendo e mapeando as estruturas de dados do sistema.

## Tabela - Usuário

| Atributo  | Chave | Tipo de dado | Tamanho | Descrição                                     |
| --------- | :---: | :----------: | :-----: | --------------------------------------------- |
| id        |  PK   |   NUMERIC    |    4    | Identificador incremental de usuário.         |
| nome      |  NN   | VARCHAR[100] |   100   | Nome real do usuário.                         |
| username  |  NN   | VARCHAR[16]  |   16    | Nome do usuário no sistema.                   |
| senha     |  NN   | VARCHAR[256] |   256   | Senha utilizada pelo usuário.                 |
| dataNasc  |  NN   |     DATE     |    3    | Data formato (XX-XX-XXXX).                    |
| email     |  NN   | VARCHAR[256] |   256   | Email utilizado pelo usuário.                 |
| tipo     |  NN   | VARCHAR[256] |   256   | Permissão para reserver as salas.                |

## Tabela - Ambiente

| Atributo     | Chave | Tipo de dado | Tamanho | Descrição                                      |
| ------------ | :---: | :----------: | :-----: | ---------------------------------------------- |
| id           |  PK   |   NUMERIC    |    4    | Identificador incremental de projeto.          |
| nome         |  NN   | VARCHAR[100] |   100   | Nome do projeto.                               |
| descricao    |  NN   | VARCHAR[280] |   280   | Descrição do projeto.                          |
| dataDeCriacao|  NN   |     DATE     |    3    | Data formato (XX-XX-XXXX).                     |
| dataReservaInic      |  NN   |     DATE     |    3    | Data formato (XX-XX-XXXX)
| dataReservaFim      |  NN   |     DATE     |    3    | Data formato (XX-XX-XXXX).                     |
| tipo      |  NN   |   NUMERIC    |    1    | Chave para diferentes tipos de ambientes.                        |
|capacidade|  NN   |   NUMERIC    |     4     | Capacidade do ambiente.                                    |
|participante|  FK   |   NUMERIC    |     4     | Id do usuário que reserva o ambiente.                                    |