# Readme do Projeto de Coleta de Variação Cambial de Criptomoedas

Este projeto consiste em uma DAG (Directed Acyclic Graph) que coleta a variação cambial de algumas criptomoedas e retorna um print mostrando qual criptomoeda teve a maior variação. O projeto foi desenvolvido para ser executado no Apache Airflow.

## Pré-requisitos

Antes de iniciar a execução do projeto, é necessário ter instalado o Docker em sua máquina. 

## Instalação e Execução

Para iniciar a execução do projeto, siga os seguintes passos:

1. Faça o clone deste repositório em sua máquina.
2. Abra o terminal na pasta raiz do projeto.
3. Execute o comando `docker build -t my-airflow .` para criar a imagem base do Airflow com as dependências necessárias.
4. Execute o comando `docker-compose up` para iniciar o Airflow.
5. No seu navegador, acesse `localhost:8080` para acessar o painel do Airflow.
7. Na aba DAGs do painel do Airflow, habilite a DAG `diario_de_criptos_DAG` e clique em "Trigger DAG" para iniciar a execução.

## Descrição da DAG

A DAG `diario_de_criptos_DAG` é composta pelos seguintes passos:

1. `begin`: tarefa que inicia a DAG.
2. `verificacao_de_endpoint`: tarefa que coleta os dados de variação cambial das criptomoedas utilizando a API CoinGecko.
3. `escolher_criptomoeda_de_maior_variacao*`: tarefa que analisa os dados coletados e retorna qual criptomoeda teve a maior variação.
4. `end`: tarefa que finaliza a DAG.

## Estrutura do Projeto

- O arquivo `docker-compose.yml` é responsável por configurar a imagem base do Airflow e executar o serviço.
- O arquivo `Dockerfile` é responsável por construir a imagem base do Airflow com as dependências necessárias.
- O arquivo `requirements.txt` contém as dependências do projeto.
- O diretório `dags/` contém o arquivo `dag-cripto.py`, que é responsável por definir a DAG.
