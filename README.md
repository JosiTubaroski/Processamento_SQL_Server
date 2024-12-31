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

  
    
