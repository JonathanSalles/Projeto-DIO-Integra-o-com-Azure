# Projeto-DIO-Integra-o-com-Azure

# [cite_start]Desafio de Projeto: Integrando Dados com MySQL Azure e Transformando com Power BI [cite: 2]

Este documento descreve as etapas para a execução de um projeto de integração de dados, que envolve a criação de uma instância MySQL no Azure, a conexão com o Power BI e a subsequente transformação dos dados.

---

## [cite_start]Ementa - Etapas do Desafio [cite: 3]

1.  **Infraestrutura na Azure**
    * [cite_start]Criar uma instância do MySQL na Azure[cite: 5, 12].
    * [cite_start]Configurar regras no Firewall da Azure para permitir o acesso ao banco de dados[cite: 8].
    * [cite_start]Conectar-se ao banco de dados via Cloud Shell e MySQL Workbench[cite: 7, 9].

2.  **Carga e Integração de Dados**
    * [cite_start]Criar o banco de dados utilizando o script disponível no GitHub[cite: 13].
    * [cite_start]Realizar a integração do Power BI com a instância MySQL na Azure[cite: 10, 14].

3.  **Transformação de Dados no Power BI**
    * [cite_start]Analisar a base de dados para identificar a necessidade de transformações[cite: 15].
    * Aplicar as diretrizes de transformação para preparar os dados para análise.

---

## [cite_start]Diretrizes para Transformação dos Dados [cite: 16]

### Análise e Limpeza Inicial

* [cite_start]**Verificar Cabeçalhos e Tipos de Dados:** Realize uma inspeção completa nos cabeçalhos e nos tipos de dados de cada coluna[cite: 17].
* [cite_start]**Modificar Tipos Monetários:** Altere os valores monetários para o tipo `double preciso` para garantir a exatidão nos cálculos[cite: 18].
* [cite_start]**Analisar e Tratar Nulos:** Verifique a existência de valores nulos e avalie a necessidade de removê-los[cite: 19].
    * [cite_start]Funcionários com valores nulos na coluna `Super_ssn` podem ser gerentes[cite: 20]. [cite_start]Verifique se existem colaboradores sem um gerente atribuído[cite: 20].
    * [cite_start]Identifique se há departamentos sem gerentes[cite: 21]. [cite_start]Caso encontre, preencha os dados ausentes[cite: 22].
* [cite_start]**Verificar Horas de Projeto:** Analise a consistência dos dados referentes ao número de horas dos projetos[cite: 23].
* [cite_start]**Separar Colunas Complexas:** Divida as colunas que contêm múltiplas informações em colunas distintas[cite: 24].

### Modelagem e Enriquecimento de Dados

* [cite_start]**Mesclar Consultas (Employee e Departament):** Combine as consultas `employee` e `departament` para criar uma tabela de funcionários que inclua o nome de seus respectivos departamentos[cite: 25]. [cite_start]A mesclagem deve ter a tabela `employee` como base[cite: 26].
* [cite_start]**Unificar Nomes dos Colaboradores:** Mescle as colunas de Nome e Sobrenome para formar uma única coluna com os nomes completos dos colaboradores[cite: 31].
* [cite_start]**Associar Gerentes a Colaboradores:** Realize a junção dos dados para exibir os nomes dos gerentes ao lado de seus respectivos colaboradores[cite: 28]. [cite_start]Este processo pode ser feito tanto com uma consulta SQL quanto pela mescla de tabelas no Power BI[cite: 29].
* [cite_start]**Criar Identificador Único de Departamento:** Mescle os nomes dos departamentos com suas localizações[cite: 32]. [cite_start]Essa ação cria uma combinação única que auxiliará na futura criação de um modelo estrela[cite: 32, 33].

> **Observação sobre Mesclar vs. Atribuir**
> [cite_start]A operação de **mesclar** foi utilizada porque o objetivo era enriquecer uma tabela com informações (colunas) de outra[cite: 35]. [cite_start]As tabelas possuem estruturas e propósitos diferentes[cite: 35]. [cite_start]A operação de **atribuir** (acrescentar) não seria adequada, pois ela empilha os dados (linhas) de uma tabela embaixo da outra[cite: 35].

### Agrupamento e Finalização

* [cite_start]**Agrupar Dados por Gerente:** Agrupe os dados para quantificar quantos colaboradores existem por gerente[cite: 36].
* [cite_start]**Eliminar Colunas Desnecessárias:** Remova as colunas que não serão utilizadas no relatório final de cada uma das tabelas[cite: 27, 37].
