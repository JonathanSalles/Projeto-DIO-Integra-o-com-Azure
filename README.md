# Projeto-DIO-Integra-o-com-Azure

Desafio de Projeto: Integrando Dados com MySQL Azure e Transformando com Power BI
Este documento detalha as etapas e diretrizes para um projeto de Business Intelligence, desde a criação de uma infraestrutura de dados na nuvem com Azure MySQL até a transformação e modelagem dos dados utilizando o Power BI.


Ementa do Desafio
O projeto é dividido em três fases principais:

Configuração da Infraestrutura no Azure

Criação e exploração da instância do Banco de Dados MySQL.

Configuração de conectividade via Cloud Shell e regras de Firewall.

Conexão e Carga de Dados

Conexão ao banco de dados via MySQL Workbench.

População do banco de dados com a base disponível no GitHub.

Integração e importação dos dados para o Power BI.


Transformação de Dados no Power BI

Análise da base de dados para identificar problemas e oportunidades de transformação.

Aplicação de uma série de transformações para limpar, modelar e enriquecer os dados para análise.

Diretrizes para a Transformação dos Dados
A seguir estão os passos recomendados para a etapa de tratamento e modelagem dos dados no Power BI.

Análise e Limpeza Inicial
Validação de Cabeçalhos e Tipos de Dados

Inspecione todas as colunas para garantir que os cabeçalhos e os tipos de dados estejam corretos.

Ajuste de Valores Monetários

Converta todas as colunas que representam valores monetários para o tipo de dado 

double preciso para garantir a exatidão nos cálculos.

Tratamento de Dados Ausentes (Nulos)

Identifique a presença de valores nulos e defina uma estratégia para tratá-los.

Investigue os funcionários com valores nulos na coluna 

Super_ssn, pois podem indicar cargos de gerência.

Verifique se algum departamento está sem gerente e, se necessário, preencha a informação.

Estruturação e Enriquecimento de Dados
Mesclagem de Consultas: Colaboradores e Departamentos

Combine as tabelas 

employee e departament para associar cada colaborador ao seu respectivo departamento. A mescla deve ter a tabela 

employee como base.

Unificação de Nomes dos Colaboradores

Mescle as colunas de nome e sobrenome para formar uma única coluna com os nomes completos dos colaboradores.

Associação de Gerentes a Colaboradores

Realize uma junção para exibir os nomes dos gerentes ao lado de seus respectivos colaboradores, seja via SQL ou mescla no Power BI.

Criação de Chave Única: Departamento-Localização

Combine as informações de nome do departamento e sua localização para criar um identificador único, auxiliando na futura criação de um modelo estrela.

Nota sobre a Escolha da Operação: Mesclar vs. Atribuir
A operação de 

Mesclar é utilizada neste projeto para adicionar novas colunas a uma tabela a partir de outra. As tabelas têm estruturas e propósitos diferentes. A operação 

Atribuir (Acrescentar), por outro lado, é usada para empilhar linhas de tabelas com a mesma estrutura.

Agrupamento e Finalização
Contagem de Colaboradores por Gerente

Utilize a funcionalidade de agrupamento para saber quantos colaboradores existem por gerente.

Otimização do Modelo

Remova as colunas desnecessárias que não serão usadas no relatório final para melhorar a performance.

Agrupamento e Finalização
Contagem de Colaboradores por Gerente

Utilize a funcionalidade de agrupamento para saber quantos colaboradores existem por gerente.

Otimização do Modelo

Remova as colunas desnecessárias que não serão usadas no relatório final para melhorar a performance.
