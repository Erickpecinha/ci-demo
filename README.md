Pipeline de Continuous Integration com GitHub Actions
1. Descrição do projeto

Este projeto apresenta a implementação de um pipeline simples de Continuous Integration (CI) utilizando o GitHub Actions.

O pipeline foi configurado para executar automaticamente um script sempre que ocorre um push no repositório, permitindo validar o funcionamento do projeto de forma automatizada.

2. Objetivo da atividade

O objetivo desta atividade é demonstrar como configurar um pipeline de integração contínua utilizando o GitHub Actions.

Com isso, sempre que houver uma atualização no repositório, o GitHub executará automaticamente um fluxo de trabalho que roda um script definido no projeto.

Essa automação ajuda a garantir que o código esteja funcionando corretamente após cada alteração.

3. Estrutura do projeto

A estrutura do projeto é composta pelos seguintes arquivos:

.github/workflows/ci.yml
script.sh
README.md

Descrição dos arquivos:

.github/workflows/ci.yml
Arquivo responsável por definir o workflow do GitHub Actions, onde está configurado o pipeline de CI.

script.sh
Script executado pelo pipeline. Ele contém os comandos que serão rodados automaticamente durante o processo de integração.

README.md
Arquivo de documentação do projeto, explicando o funcionamento do pipeline e a estrutura utilizada.

4. Explicação do workflow

O arquivo ci.yml define o comportamento do pipeline dentro do GitHub Actions.

Exemplo de configuração:

name: CI Pipeline

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Clonar repositório
        uses: actions/checkout@v3

      - name: Executar script
        run: bash script.sh

Explicação de cada parte:

name: CI Pipeline
Define o nome do workflow que será exibido na aba Actions do GitHub.

on: [push]
Define que o pipeline será executado sempre que ocorrer um push no repositório.

jobs:
Define os trabalhos que serão executados no pipeline.

build:
Nome do job responsável pela execução das etapas.

runs-on: ubuntu-latest
Define que o job será executado em uma máquina virtual com sistema operacional Ubuntu.

steps:
Define as etapas que serão executadas no job.

actions/checkout@v3
Ação responsável por clonar o repositório dentro do ambiente de execução do pipeline.

run: bash script.sh
Executa o script script.sh presente no repositório.

5. Fluxo do pipeline

O fluxo de execução do pipeline funciona da seguinte forma:

Push no GitHub
      ↓
GitHub Actions detecta a mudança
      ↓
Execução do workflow (ci.yml)
      ↓
Clonagem do repositório
      ↓
Execução do script.sh
      ↓
Exibição do resultado no GitHub Actions
6. Resultado da execução

Quando um push é realizado no repositório, o GitHub automaticamente inicia o pipeline definido no arquivo ci.yml.

Durante a execução:

O GitHub cria um ambiente virtual utilizando Ubuntu.

O repositório é clonado para esse ambiente.

O script script.sh é executado.

O resultado da execução é exibido na aba Actions do GitHub.

Se o script for executado com sucesso, o pipeline será marcado como concluído com sucesso (✔).
Caso ocorra algum erro, o pipeline será marcado como falho (✖), permitindo identificar rapidamente o problema.
