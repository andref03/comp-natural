# Algoritmo Genético para o Problema das N-Rainhas

Este repositório contém implementações de Algoritmos Genéticos (AG) para resolver o clássico Problema das N-Rainhas. O objetivo é posicionar N rainhas em um tabuleiro de xadrez N×N de forma que nenhuma rainha ataque outra.

## 1. O Problema das N-Rainhas

O Problema das N-Rainhas é um desafio combinatório onde se busca encontrar configurações válidas para N rainhas em um tabuleiro N×N. Uma configuração é considerada válida se nenhuma rainha estiver na mesma linha, coluna ou diagonal que outra rainha.

## 2. Abordagem com Algoritmos Genéticos

Utilizamos Algoritmos Genéticos para explorar o espaço de soluções do problema das N-Rainhas. A abordagem consiste em:

- **Representação**: Cada indivíduo na população é representado por um vetor de inteiros de tamanho N, onde o índice do vetor representa a coluna e o valor em cada posição representa a linha onde a rainha está posicionada. Por exemplo, `[1, 3, 0, 2]` para N=4 significa que a rainha na coluna 0 está na linha 1, na coluna 1 na linha 3, e assim por diante.
- **Função de Fitness (Conflitos)**: A função de fitness avalia a qualidade de cada indivíduo (solução). Neste projeto, o fitness é calculado com base no número de pares de rainhas que se atacam. O objetivo é minimizar este valor, sendo 0 o fitness ideal (nenhum ataque).
- **Operadores Genéticos**:
    - **Seleção**: Utiliza-se a seleção por torneio binário para escolher os pais.
    - **Cruzamento**: O cruzamento é realizado em um ponto de corte aleatório, combinando partes dos vetores dos pais para gerar novos filhos.
    - **Mutação**: A mutação é aplicada aos filhos, alterando aleatoriamente a posição de uma rainha em uma coluna para introduzir diversidade na população.
- **Estratégias de Substituição de População (alternativa)**: A versão alternativa do algoritmo explora diferentes métodos de como a nova geração é formada a partir dos pais e filhos, incluindo:
    - Substituição total (sem elitismo)
    - Substituição total (com elitismo)
    - Manter k melhores pais
    - Inserir k melhores filhos
    - Pais + filhos -> melhores
    - Pais + filhos -> aleatório

## 3. Estrutura do Repositório

O repositório está organizado da seguinte forma:

- `queens/`:
    - `queens_versao_basica.ipynb`: Contém a implementação da versão básica do algoritmo genético para o problema das N-Rainhas.
    - `queens_alternativa_03.ipynb`: Apresenta uma versão alternativa do algoritmo, explorando diferentes estratégias de substituição de população e configurações para N=8, 15, 20 e 30.

## 4. Como Executar

Para replicar os experimentos e análises, siga os passos abaixo:

1.  **Clonar o Repositório**:
    ```bash
    git clone https://github.com/andref03/comp-natural.git
    cd comp-natural/queens
    ```

2.  **Instalar Dependências**:
    Os notebooks utilizam bibliotecas Python comuns para computação numérica e visualização. É recomendável criar um ambiente virtual:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    pip install numpy matplotlib pandas jupyter
    ```

3.  **Executar os Notebooks**:
    Abra os notebooks Jupyter e execute as células para ver as implementações e os resultados dos experimentos:
    ```bash
    jupyter notebook
    ```
    Navegue até a pasta `queens` e abra `queens_versao_basica.ipynb` e `queens_alternativa_03.ipynb`.

## 5. Resultados e Análise

Os resultados detalhados dos experimentos, incluindo tabelas comparativas de tempo de execução, número de gerações para convergência, taxa de sucesso e análise crítica sobre o impacto do aumento do espaço de busca (N=30) e o ajuste de parâmetros, estão disponíveis no relatório gerado. Este relatório discute como diferentes estratégias de substituição e parâmetros afetam a eficiência do algoritmo.
