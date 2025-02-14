# Algoritmo Genético para o Knapsack Problem

Este repositório contém a implementação de um **algoritmo genético** para resolver o **knapsack problem**. O Knapsack Problem é um problema clássico de otimização combinatória, onde o objetivo é maximizar o valor de itens incluídos numa mochila sem exceder a sua capacidade.

## Descrição do Algoritmo

O algoritmo genético é um método de busca estocástica que simula o processo de seleção natural. Ele utiliza operações de **seleção**, **crossover** (recombinação), **mutação** e **elitismo** para gerar uma população de soluções e evoluí-las ao longo de várias gerações.

Este código implementa as operações de:
- **Seleção**: Escolha dos melhores indivíduos da população baseada no valor do **fitness**.
- **Crossover**: Combinação de duas soluções para gerar novas soluções.
- **Mutação**: Introdução de pequenas mudanças aleatórias para explorar novas soluções.
- **Elitismo**: Garantia de que as melhores soluções de uma geração são mantidas.

## Estrutura do Código

1. **Função `fitness`**: Calcula o valor total dos itens selecionados na mochila, verificando se o peso total não excede a capacidade da mochila.
2. **Função `mutacao`**: Aplica mutação aleatória nos cromossomos para garantir diversidade na população.
3. **Função `crossover`**: Realiza a operação de crossover de um ponto entre dois cromossomos.
4. **Função `selecao`**: Seleciona os pais para reprodução com base no valor de fitness, utilizando um método de **roleta**.
5. **Algoritmo Genético**: Realiza a evolução da população através de um número definido de gerações, utilizando **elitismo**, **crossover** e **mutação**.

## Parâmetros do Problema

- **n**: Número de itens na mochila.
- **capacidade**: Capacidade máxima da mochila.
- **pesos**: Lista com os pesos dos itens.
- **valores**: Lista com os valores dos itens.

## Parâmetros do Algoritmo Genético

- **populacao_size**: Tamanho da população em cada geração.
- **geracoes**: Número de gerações para o algoritmo evoluir.
- **taxa_mutacao**: Taxa de probabilidade de ocorrer mutação em um cromossomo.
- **taxa_crossover**: Probabilidade de ocorrência de crossover entre dois pais.
- **elite_size**: Número de melhores indivíduos que são mantidos entre as gerações (elitismo).

## Como Usar

1. Clone o repositório:

```bash
git clone https://github.com/beatrizzoliveira/knapsack-problem.git
```

2. Instale as dependências necessárias:

```bash
pip install -r requirements.txt
```

3. Execute o script principal para rodar o algoritmo genético:

```bash
python knapsack_problem.py
```

O código irá executar o algoritmo genético e ao final imprimirá a melhor solução encontrada, bem como um gráfico mostrando a evolução do **fitness** ao longo das gerações.

## Exemplo de Saída

```
Melhor solução encontrada: [1, 1, 1, 0, 0, 1, 0, 1, 1, 0] com valor total de 1800
```

Este resultado indica quais foram os itens selecionados para a mochila (onde 1 significa que o item foi escolhido e 0 significa que não foi escolhido) e o valor total obtido.

## Gráfico de Evolução do Fitness

Após a execução, o código irá gerar um gráfico mostrando como o valor de **fitness** (valor total dos itens na mochila) evolui ao longo das gerações. Isso ajuda a visualizar a melhoria das soluções ao longo do tempo.

## Arquivos

- **knapsack_problem.py**: O código principal do algoritmo genético.
- **requirements.txt**: Arquivo com as dependências do projeto.
- **README.md**: Este arquivo.

## Dependências

- **Python 3.x**
- **matplotlib**: Biblioteca para gerar gráficos.
  
Instale as dependências com o seguinte comando:

```bash
pip install matplotlib
```

## Como Funciona

1. **Inicialização**: A população inicial é criada de forma aleatória, onde cada indivíduo (cromossomo) é representado por uma sequência binária. Cada bit da sequência indica se um item está incluído na mochila (1) ou não (0).
   
2. **Cálculo de Fitness**: O valor de fitness de cada cromossomo é calculado, levando em consideração o valor dos itens e a capacidade da mochila.

3. **Seleção**: Os indivíduos com maior fitness têm mais chances de ser selecionados para reprodução.

4. **Crossover**: Durante o crossover, dois cromossomos são escolhidos e um ponto de corte é determinado aleatoriamente para recombinar os genes dos pais e gerar novos filhos.

5. **Mutação**: Após o crossover, é aplicada uma mutação nos cromossomos, o que pode alterar aleatoriamente alguns bits, introduzindo novas soluções.

6. **Elitismo**: Os melhores indivíduos da geração atual são preservados diretamente para a próxima geração, garantindo que as melhores soluções nunca sejam descartadas.

7. **Evolução**: Esse processo é repetido por um número determinado de gerações, com a população evoluindo e as soluções melhorando ao longo do tempo.

## Contribuições

Caso tenha sugestões ou melhorias, poderá abrir uma **issue** ou enviar um **pull request**.

## Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para mais detalhes.
