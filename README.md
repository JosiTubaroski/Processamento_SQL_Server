<div> 
<p><a href="https://github.com/JosiTubaroski/Introducao_Engenharia_Dados/blob/main/README.md">Introdução a Engenharia de Dados</a></p>
</div> 

# Caso de uso de processamento de dados utilizando SQL Server

### Caso de Uso Prático: Pipeline de ETL para Processamento de Dados de Vendas com SQL Server

#### Cenário:

Uma empresa de e-commerce deseja analisar dados de vendas para entender padrões de comportamento dos clientes. Os dados vêm de diferentes fontes:

- Sistema de Pedidos: Contém informações de pedidos em tempo real (transacional).
- Sistema de Marketing: Contém dados sobre campanhas publicitárias e interações dos clientes.
- Sistema de Logística: Contém dados de entrega e devoluções.

Esses dados precisam ser integrados, transformados e analisados para gerar relatórios de performance de vendas e insights estratégicos.

#### Objetivo:

Construir um pipeline de ETL (Extração, Transformação e Carga) para consolidar os dados em um Data Warehouse no SQL Server, de forma que relatórios possam ser facilmente gerados.

#### Passo a Passo:

##### 1. Extração dos Dados

- Dados são extraídos de:
  - Sistema de Pedidos (SQL Server): Consultas diretas às tabelas transacionais.
  - Sistema de Marketing (API externa): Dados importados em formato JSON/CSV.
  - Sistema de Logística (Arquivo CSV): Dados fornecidos diariamente.

##### Ferramentas Utilizadas:

- Utilização de scripts SQL e SSIS (SQL Server Integration Services) para extrair dados diretamente do SQL Server e carregar os arquivos CSV.

  <img src="https://github.com/JosiTubaroski/Processamento_SQL_Server/blob/main/img/01_Script_CSV.png">
    
##### 2. Transformação dos Dados

- Limpeza de Dados:
  - Remoção de duplicatas e registros inválidos.
  - Tratamento de campos nulos, substituindo por valores padrão ou marcando como "Desconhecido".
    
 <img src="https://github.com/JosiTubaroski/Processamento_SQL_Server/blob/main/img/02_Limpeza_Dados.png">

 - Cálculos e Agregações:
   - Calcular valores como receita total, margem de lucro, e tempo médio de entrega.
     
<img src="https://github.com/JosiTubaroski/Processamento_SQL_Server/blob/main/img/03_Agregacao.png">
   
 - Join entre fontes:

   - Unir dados de diferentes sistemas, como associar informações de pedidos às campanhas de marketing

<img src="https://github.com/JosiTubaroski/Processamento_SQL_Server/blob/main/img/04_Exe_Join.png">
    
##### 3. Carga no Data Warehouse

Os dados transformados são carregados em tabelas dimensionais e factuais no Data Warehouse para facilitar a geração de relatórios.

Estrutura típica:

  - Dimensão Cliente: Contém informações dos clientes.
  - Dimensão Produto: Contém informações dos produtos vendidos.
  - Fato Vendas: Contém dados de vendas agregados por cliente, produto e data.

<img src="https://github.com/JosiTubaroski/Processamento_SQL_Server/blob/main/img/05_Insert_FatoVenda.png">

##### 4. Geração de Relatórios

Os dados no Data Warehouse são acessados por ferramentas de BI, como Power BI ou Tableau, para criar relatórios como:

 - Receita por região e período.
 - Performance de campanhas de marketing.
 - Análise de devoluções.

## Benefícios:

1. Centralização dos Dados: Todas as fontes são integradas em um único lugar.
2. Performance: O uso de um Data Warehouse otimiza a consulta de grandes volumes de dados.
3. Flexibilidade: Os dados transformados podem ser usados para diversas análise estratégicas.
4. Automação: Com o uso de SSIS e scripts SQL, o processo de ETL pode ser agendado para rodar automaticamente.

Esse é um exemplo prático de como o SQL Server pode ser utilizado para resolver problemas de processamento de dados, desde a coleta de informações até a entrega de dados acionáveis.
