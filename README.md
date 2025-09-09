# Projeto-DIO-Integra-o-com-Azure
# [cite_start]Desafio de Projeto: Integrando Dados com MySQL Azure e Transformando com Power BI [cite: 1, 2]

[cite_start]Este projeto descreve o processo de integração de dados de um banco de dados MySQL hospedado no Azure com o Power BI, com foco na transformação e preparação dos dados para análise. [cite: 2]

---

## [cite_start]Ementa - Etapas do Desafio [cite: 3]

1.  **Criação e Configuração no Azure:**
    * [cite_start]Criar uma instância do MySQL no Azure. [cite: 5]
    * [cite_start]Explorar o recurso da instância do MySQL. [cite: 6]
    * [cite_start]Conectar-se ao Banco de Dados via Cloud Shell. [cite: 7]
    * [cite_start]Criar regras de firewall no Azure para permitir acesso externo. [cite: 8]

2.  **Conexão e Carga de Dados:**
    * [cite_start]Conectar ao MySQL no Azure utilizando o Workbench. [cite: 9]
    * [cite_start]Criar o banco de dados a partir da base disponível no GitHub. [cite: 13]
    * [cite_start]Integrar o Power BI com o MySQL no Azure para importar os dados. [cite: 10, 14]

3.  **Transformação de Dados no Power BI:**
    * [cite_start]Analisar a base de dados para identificar problemas e oportunidades de transformação. [cite: 15]
    * [cite_start]Aplicar uma série de transformações para limpar, modelar e enriquecer os dados. [cite: 16]

---

## [cite_start]Diretrizes para Transformação dos Dados [cite: 16]

### Análise e Limpeza Inicial

- [ ] [cite_start]**Verificar Cabeçalhos e Tipos de Dados:** Garanta que todas as colunas tenham nomes claros e que os tipos de dados (texto, número, data) estejam corretos. [cite: 17]
- [ ] [cite_start]**Modificar Valores Monetários:** Altere os tipos de dados de colunas monetárias para um formato numérico preciso, como `double`. [cite: 18]
- [ ] **Tratamento de Nulos:**
    - [cite_start]Verifique a existência de valores nulos e decida sobre a melhor abordagem (remoção ou preenchimento). [cite: 19]
    - [cite_start]Para a coluna `Super_ssn` na tabela `employees`, investigue os valores nulos, pois eles podem indicar os funcionários que são gerentes. [cite: 20]
    - [cite_start]Verifique se há algum departamento sem gerente e, caso exista, preencha a informação. [cite: 21, 22]
- [ ] [cite_start]**Verificar Horas do Projeto:** Analise a coluna de horas dos projetos para garantir a consistência dos dados. [cite: 23]
- [ ] [cite_start]**Separar Colunas Complexas:** Se houver colunas com informações compostas, divida-as em colunas separadas para facilitar a análise. [cite: 24]

### Estruturação e Enriquecimento de Dados

- [ ] **Mesclar Consultas (Employee e Departament):**
    - [cite_start]Combine as tabelas `employee` e `departament` para associar cada colaborador ao seu respectivo departamento. [cite: 25]
    - [cite_start]A mescla deve ter a tabela `employee` como base. [cite: 26]

- [ ] **Mesclar Nomes de Colaboradores:**
    - [cite_start]Combine as colunas de nome e sobrenome (`Fname` e `Lname`) para criar uma única coluna com o nome completo do colaborador. [cite: 31]

- [ ] **Associar Colaboradores e Gerentes:**
    - [cite_start]Realize uma junção (via mescla de tabelas no Power BI ou com uma consulta SQL) para exibir o nome do gerente ao lado do nome de cada colaborador. [cite: 28, 29]

- [ ] **Criar Chave Única de Departamento-Local:**
    - [cite_start]Mescle as colunas de nome do departamento e localização para criar um identificador único para cada combinação. [cite: 32]
    - [cite_start]> **Nota:** Esta etapa é fundamental para a futura criação de um modelo em esquema estrela. [cite: 33]

### Agrupamento e Finalização

- [ ] [cite_start]**Agrupar Colaboradores por Gerente:** Agrupe os dados para obter a contagem de quantos colaboradores estão sob a responsabilidade de cada gerente. [cite: 36]
- [ ] [cite_start]**Otimização do Modelo:** Elimine todas as colunas que não serão utilizadas nos relatórios finais para melhorar a performance e a usabilidade do modelo. [cite: 27, 37]

### Justificativa de Uso: Mesclar vs. Atribuir

> **Por que usar "Mesclar" e não "Atribuir"?**
>
> Neste cenário, a operação correta é **Mesclar** (Merge). As tabelas `employee` e `departament` possuem propósitos e estruturas diferentes. O objetivo é enriquecer a tabela de colaboradores adicionando informações (colunas) da tabela de departamentos. [cite_start]A operação **Atribuir** (Append), por outro lado, é utilizada para empilhar tabelas que possuem a mesma estrutura, adicionando novas linhas de dados. [cite: 35]
