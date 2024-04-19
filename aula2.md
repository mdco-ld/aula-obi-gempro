# Complexidade e arrays (vectors)

## Introdução

Em programação competitiva, é importante não só que a sua solução seja correta, como também que ela seja eficiente.
Tendo isso em mente, como podemos saber se uma solução é eficiente o bastante para um problema?

## Complexidade

Complexidade é uma das formas que temos de calcular o limite do número de operações que serão executadas no seu código, dependendo do tamanho do input.
O que isso quer dizer? Vejamos um exemplo prático.

Exemplo 1
```cpp
#include <iostream>

using namespace std;

int main() {
    int n;
    cin >> n;
    // Calcular 1 + 2 + ... + n
    int soma = 0;
    for (int i = 1; i <= n; i++) {
        soma += i;
    }
    cout << soma << endl;
    return 0;
}
```

Esse código calcula a soma `1 + 2 + ... + n`, e utiliza um loop para fazer isso. Pergunta: Quantas vezes o código no loop será executado?
Isso depende do input, mas de forma geral, o código será executado `n` vezes.
Em situações assim, dizemos que o algoritmo possui complexidade `O(n)`.

Exemplo 2
```cpp
#include <iostream>

using namespace std;

bool is_prime(int p) {
    if (p < 2) {
        return false;
    }
    if (p == 2) {
        return true;
    }
    for (int i = 2; i < p; i++) {
        if (p % i == 0) {
            return false;
        }
    }
    return true;
}

int main() {
    int n;
    cin >> n;
    // Contar numero de primos menores que n
    int count = 0;
    for (int i = 2; i < n; i++) {
        if (is_prime(i)) {
            count++;
        }
    }
    cout << count << endl;
    return 0;
}
```

Primeiramente, vamos analisar a função `is_prime`. A primeira coisa que ela faz é verificar se `p` é menor que `2`. Isso consiste de uma única operação, logo é `O(1)`. Logo depois, ela verifica se `p` é igual a `2`, que também consiste de uma única operação. Logo, também é `O(1)`.
Depois disso, temos um loop, que não sabemos quantas vezes será executado: Se `p` for primo, o loop será executado até acabar, mas se `p` não for primo, ele retornará antes de acabar. Em situações assim, podemos assumir o pior caso. Logo, essa parte do algoritmo é `O(n)`.
Com isso, vemos que a complexidade do algoritmo é `O(n + 2)`, mas ao calcular a complexidade, apenas consideramos a maior função quando `n` cresce, neste caso, `n`.
Outros exemplos: 
- `O(n^2 + n + 1)` -> `O(n^2)`
- `O(n^3 - n^2)` -> `O(n^3)`
- `O(5n)` -> `O(n)`
- `O(log(n) + 15)` -> `O(log(n))`

Agora, vamos analisar a função `main`. o loop é executado `n` vezes, mas dentro do loop chamamos a função `is_prime` a cada iteração. Como `is_prime` é `O(n)` e ela é executada `n` vezes, a complexidade total é `O(n^2)`.

Para saber se um algoritmo é eficiente o bastante em competições de programação, calculamos a complexidade do algoritmo, e consideramos o tamanho do input. Se o número de operações for no máximo `10^8`

Exemplos:
- `n <= 10^7`, algoritmo = `O(n)` -> total = `10^7` -> funciona
- `n <= 10^5`, algoritmo = `O(n^2)` -> total = `10^10` -> não funciona
- `n <= 10^2`, algoritmo = `O(n^3)` -> total = `10^6` -> funciona
- `n <= 10^6`, algoritmo = `O(n log(n))` -> total = `2*10^7` -> funciona
