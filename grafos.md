# Introdução Grafos Resumo

## Definições

Formalmente, um grafo é um par (V, E), onde V é um conjunto de *vértices*, e E é um conjunto de *arestas*.
Arestas são pares de elementos de V, indicando que estes elementos estão conectados

Em grafos simples, só pode existir no máximo uma aresta entre dois vértices. Quando pode existir mais de uma aresta ligando dois vértices, o grafo é chamado *multigrafo*.

O *grau* de um vértice `deg(v)` é o número de arestas que possuem esse vértice.

Um *caminho* é uma sequência de vértices conectados.

Um *ciclo* é um caminho de tamanho maior ou igual a 3 cujo vértice final está conectado ao vértice inicial.

Um *caminho euclidiano* é um caminho que passa por cada **aresta** do grafo exatamente uma vez.

Um *caminho hamiltoniano* é um caminho que passa por cada **vértice** do grafo exatamente uma vez.

Um grafo é chamado *acíclico* se ele não possui ciclos.

Dois vértices estão *conectados* se existe um caminho que possui os dois vértices.

Um grafo é chamado *conexo* se quaisquer dois vértices nesse grafo estão conectados por um caminnho.

Uma *componente conexa* de um grafo é um conjunto de vértices desse grafo que estão todos contectados.

Uma *árvore* é um grafo conexo e acíclico.

Um grafo é chamado *bipartido* se os vértices dele podem ser divididos em dois grupos de forma que cada aresta conecta vértices de grupos diferentes.

Um grafo é chamado *completo* se quaisquer dois vértices estão conectados por uma aresta.

## Propriedades

- A soma dos graus dos vértices de um grafo é igual a duas vezes o número de arestas.
- Um grafo possui um caminho euclidiano se e somente se ele é conexo, e o número de vértices de grau ímpar é igual a 0 ou 2.
- Uma árvore com `n` vértices possui `n - 1` arestas.
- Numa árvore, existe exatamente um caminho entre cada par de vértices.
- Um grafo é bipartido se e somente se ele não possui ciclos de comprimento ímpar.
- Um grafo completo de `n` vértices possui exatamente `n(n - 1)/2` arestas.

## Representação de um grafo

Lista de adjacência
```cpp
vector<vector<int>> edges;

edges.resize(n);

// 5 é adjacente a 0, 3, 4, e 7
edges[5] = {0, 3, 4, 7};
```

Matriz de adjacência
```cpp
vector<vector<int>> adj;

adj.resize(n);
for (int i = 0; i < n; i++) {
    adj.resize(n);
}

// 3 é adjacente a 5
adj[3][5] = 1;
adj[5][3] = 1;
```
