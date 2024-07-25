# README para Desafio Módulo 3 - Processamento de Dados Simplificado com Power BI

## Descrição do Projeto
Este projeto tem como objetivo demonstrar o processo de configuração de uma instância MySQL na Azure, a criação de um banco de dados a partir de uma base disponível no GitHub, a integração deste banco de dados com o Power BI e a realização de várias transformações e análises de dados para preparar um relatório dinâmico e informativo.

### Etapas Principais
1. **Criação de uma instância na Azure para MySQL**: Configuração do servidor MySQL na plataforma Azure para hospedar o banco de dados necessário para o desafio.
2. **Criação do Banco de Dados**: Utilização de uma base de dados disponibilizada no GitHub para criar as tabelas necessárias no MySQL.
3. **Integração do Power BI com MySQL no Azure**: Conexão do Power BI ao banco de dados MySQL para acessar os dados diretamente na nuvem.
4. **Verificação e Transformação de Dados**: Análise e modificação dos dados para corrigir inconsistências e preparar os dados para análises mais complexas.

## Diretrizes para Transformação dos Dados
### Análise de Dados
- **Verificação de Cabeçalhos e Tipos de Dados**: Garantir que todos os dados estão corretamente categorizados e que os tipos de dados estão de acordo com as necessidades analíticas.
- **Modificação de Valores Monetários**: Conversão de todos os valores monetários para o tipo double para garantir precisão nos cálculos.
- **Análise de Dados Nulos**: Identificação de registros nulos e decisão sobre a necessidade de removê-los ou modificá-los com base no contexto dos dados.

### Integridade de Dados
- **Análise de Gerência**: Verificação de campos nulos em `Super_ssn` para identificar gerentes e verificar se todos os departamentos e colaboradores estão associados a um gerente.

### Junção e Mesclagem de Dados
- **Mesclagem de Dados de Funcionários e Departamentos**: Utilização do Power BI para mesclar dados e criar uma tabela de funcionários com os nomes dos departamentos associados.
- **Agrupamento de Dados**: Agrupamento de colaboradores por gerente para análise de distribuição de equipe.
- **Otimização de Dados**: Eliminação de colunas desnecessárias para simplificar os modelos de dados e prepará-los para relatórios.

## Configuração e Uso
### Requisitos
- Azure Subscription
- MySQL Server na Azure
- Power BI Desktop

### Configuração
1. **Instância Azure MySQL**: [Instruções para configuração](https://docs.microsoft.com/en-us/azure/mysql/)
2. **Power BI e MySQL**: [Instruções de integração](https://docs.microsoft.com/en-us/power-bi/connect-data/service-connect-to-azure-mysql)

## Queries SQL Utilizadas
```sql
-- Exemplo de Query SQL para mesclar nomes de funcionários e gerentes
SELECT a.EmployeeName, b.ManagerName
FROM Employees a
JOIN Managers b ON a.ManagerID = b.ManagerID
