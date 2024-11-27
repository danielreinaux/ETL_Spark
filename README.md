# Projeto de ETL e Estruturação de Dados com Apache Spark
### 1. Introdução
Esse projeto foi desenvolvido como parte de um desafio de ETL. O objetivo é realizar o tratamento de dados históricos de precipitação disponiblizados pelo Instituto Nacional de Metereologia (INMET), utilizando uma aruiqtetura em camadas, focando na camada de Bronze e Prata.
Os dados processados são provenientes do site: https://portal.inmet.gov.br/dadoshistoricos.

### 2. Arquitetura e Metodologia
O projeto segue a estrutura de camadas da arquitetura de dados de Medalhões:
* Camada Bronze: Armazena os dados brutos extraídos dos arquivos ZIP.
* Camada Prata: Contém os dados tratados e prontos para consumo.
* Camada Ouro (não implementado): Destinada a análises avançadas e visualizações.

#### Tecnologias Utilizadas:
* Python para extração e Manipulação dos dados.
* Apache Spark (PySpark) para transformação e normalização dos dados.
* Estrutura de diretórios para organizar os arquivos.

### 4. Fluxo do Processo ETL
#### Etapa 1: Extração e Camada Bronze:
##### 1. Extração Automática:
* Faz o download dos arquivos ZIP para os anos desejados
* Organiza os arquivos em pastas por ano

  ![image](https://github.com/user-attachments/assets/19193739-f681-41f6-87dc-7d7955cffbb3)

##### 2. Renomeação e Organização:
* Extrai e organiza os arquivos CSV, renomeando-os por Estado, Cidade, e Ano:
  ![image](https://github.com/user-attachments/assets/f3d271fa-768b-47a0-b0c5-0db8ce55de60)

#### Etapa 2: Transformação e Camada Prata 
##### 1. Normalização de Dados e Combinação de DataFrames:
![image](https://github.com/user-attachments/assets/17f06c41-de08-4ea0-9724-735c4a652436)

##### 2. Tratamento de Valores Nulos e Renomeação de Colunas Finais:
![image](https://github.com/user-attachments/assets/131358f3-cbd6-4149-8970-17219f0af71b)
![image](https://github.com/user-attachments/assets/1b5ff051-1abd-43e6-81a2-5e1d53920dc8)

### 5. Resultados e Dados Gerados
##### Tempo de Processamento:
O processamento dos dados para todos os anos levou aproximadamente 9107 segundos (2 horas e 31 minutos).
##### Exemplo do DataFrame Final:
![image](https://github.com/user-attachments/assets/cac4f0bc-8161-4390-b398-810e50eaacba)


