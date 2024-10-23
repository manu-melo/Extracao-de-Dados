# Pipeline ETL - Fake Store API

Este projeto implementa um pipeline ETL (Extract, Transform, Load) que coleta dados da Fake Store API, realiza transformações e salva os resultados em arquivos Parquet. O pipeline é executado automaticamente a cada 2 horas.

## Funcionalidades

- Extração de dados de produtos e carrinhos da Fake Store API
- Transformações automáticas dos dados incluindo:
  - Cálculos de métricas de vendas
  - Geração de dados aleatórios para simulação
  - Normalização de datas
  - Associação com lojas físicas
- Salvamento automático em formato Parquet com compressão
- Agendamento automático de execuções
- Tratamento de erros e logs
- Organização dos arquivos por timestamp

## Pré-requisitos

- Python 3.7+

## Dependências

pandas
numpy
requests
schedule
pyarrow  # para suporte ao formato parquet


#### Extract
- Coleta dados da Fake Store API:
  - Produtos: `https://fakestoreapi.com/products/`
  - Carrinhos: `https://fakestoreapi.com/carts/`

#### Transform
- Produtos:
  - Expansão de ratings
  - Cálculo de métricas de vendas
  - Geração de dados geográficos
  - Associação com lojas

- Carrinhos:
  - Normalização de datas
  - Expansão de produtos
  - Associação com lojas

#### Load
- Salvamento em formato Parquet com:
  - Compressão snappy
  - Nomenclatura com timestamp
  - Organização em diretório dedicado

## Tratamento de Erros

O pipeline inclui tratamento para:
- Falhas na API
- Dados ausentes ou malformados
- Erros de transformação
- Problemas de gravação
