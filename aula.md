# Maps

## Introdução

Em C++, `map` é uma estrutura de dados que permite associar valores de um tipo a valores de um outro tipo.

Já analisamos a ideia de usar um array como uma forma de associar certos números com valores, (e.g. quando fizemos `count['a']++`, `position['b'] = 4`, ...).
Porém, essa abordagem tem certas limitações:
- O que acontece se os índices forem muito grandes?
Neste caso, teríamos que fazer um array para acomodar todos os índices possíveis, que pode ser grande demais para caber na memória.
Se eu quiser associar o número 1000000000000 a um valor, eu teria que criar um array com no mínimo 1000000000000 posições, o que é inviável e excederia o limite de memória.
- O que fazer se eu quiser associar um tipo diferente ao valor, por exemplo, uma string.
Neste caso, não podemos usar um array, pois não é possível usar uma string como índice de um array.

## Maps

O `map` resolve ambas as limitações acima.
aqui está um exemplo de como usá-lo:
```cpp
map<string, int> mp;

mp["abc"] = 5;

cout << mp["abc"] << endl; // printa o valor 5

mp["xyz"] = 10;

if (mp.count("xyz")) { // verifica se "xyz" está no map
    cout << "Presente" << endl;
} else {
    cout << "Não Presente" << endl;
}

mp.clear(); // remove todos os elementos do map
```

O map realiza todas essas operações em O(log(n)).

**Importante**: não use `mp[x]` se você não sabe se `x` está no map, pois isso vai inserir x no map se ele não já estiver.

Exemplo:
```cpp
map<string, int> mp;

cout << mp["abc"] << endl; // Insere "abc" no map e printa o valor 0
```

## Usando maps

1. [two sum](https://leetcode.com/problems/two-sum/description/) (resolver em O(n log(n)))
2. [lecture](https://codeforces.com/problemset/problem/499/B)
