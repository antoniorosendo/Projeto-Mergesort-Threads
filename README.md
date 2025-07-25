# Projeto: Mesclagem e Ordenação Paralela de Arquivos com Threads

## Visão Geral do Projeto
Este projeto prático da disciplina de Sistemas Operacionais (TT304A) da UNICAMP - FT, implementa uma solução eficiente para o problema de mesclagem e ordenação de múltiplos arquivos de entrada contendo valores inteiros desordenados em um único arquivo de saída ordenado. A aplicação utiliza paralelismo com threads para otimizar o desempenho do processamento de dados.

O programa é capaz de trabalhar com um número específico de threads (1, 2, 4 ou 8), onde cada thread é responsável por ler e ordenar os dados de um arquivo de entrada. O algoritmo de ordenação utilizado em cada thread é o Mergesort, e os resultados parciais são então mesclados para gerar o arquivo de saída final ordenado.

## Como Compilar e Executar
Para compilar e executar o programa em sistemas Linux, siga os comandos abaixo, utilizando o `makefile` fornecido para padronizar o processo.

### Pré-requisitos
Certifique-se de ter o `gcc` e as bibliotecas `pthread` instaladas em seu ambiente Linux.

### Compilação
Utilize o comando `make` para compilar o programa. Isso executará a linha de comando padrão definida no `makefile`: `gcc -o mergesort mergesort.c -Ipthread`.

Após a compilação, um executável chamado mergesort será gerado.

### Execução:
O programa aceita como argumento o número de threads desejado (1, 2, 4 ou 8) e uma lista de arquivos de entrada .dat, além da opção -o seguida do nome do arquivo de saída.

Para facilitar a execução com diferentes configurações de threads, o makefile já possui comandos pré-definidos que utilizam 3 arquivos de entrada (arq1.dat, arq2.dat, arq3.dat).

Para executar o programa, utilize: **make <num_threads>**

**Exemplos:**
- Execução com 1 thread: make 1
- Execução com 2 threads: make 2
- Execução com 4 threads: make 4
- Execução com 8 threads: make 8

## Observação sobre arquivos de entrada: 
Embora os comandos do makefile estejam configurados para 3 arquivos de entrada, o programa é capaz de processar até 8 arquivos de entrada.

## Resultados e Análise de Desempenho: 
Os testes de desempenho mostraram que a utilização de threads pode otimizar significativamente o tempo de execução, dependendo do balanceamento de carga e da sobrecarga de gerenciamento de threads.

Conforme o gráfico de "Tempo de Execução x Número de Threads":

<img width="967" height="601" alt="image" src="https://github.com/user-attachments/assets/4e7c0b0c-e880-414b-8070-48465e1168d5" />

- 2 threads ofereceram o melhor desempenho, pois as tarefas foram divididas de forma equilibrada com menor sobrecarga de gerenciamento.
- Com 4 e 8 threads, o tempo de execução aumentou. Isso ocorreu porque o número de threads excedeu o número de arquivos de entrada utilizados nos testes (3 arquivos), resultando em threads ociosas e sobrecarga desnecessária na gerência.
- A medição do tempo de execução de cada thread e do tempo total do programa é fundamental para avaliar o desempenho e identificar gargalos. A conclusão principal é que o número de threads deve ser ajustado ao número de arquivos de entrada para otimizar o desempenho geral do sistema.

## Conclusões
Este projeto demonstra uma aplicação prática de conceitos de concorrência e paralelismo para o processamento de dados. A combinação do algoritmo Mergesort com a paralelização por threads prova ser uma solução eficiente para lidar com grandes volumes de dados desordenados, transformando-os em um único arquivo ordenado. A capacidade de otimização através do ajuste do número de threads conforme a carga de trabalho é um ponto chave desta implementação.

## Desenvolvedores do projeto
- Antonio Carlos Rosendo da Silva
- Eduardo Castro Brito
