## Função `funq3` em Haskell - Questão 3 da Prova

*Fizz buzz* é um jogo de palavras em grupo para crianças, usado para ensinar sobre divisão. Os jogadores se revezam para contar de forma incremental, substituindo qualquer número divisível por três pela palavra "Fizz", qualquer número divisível por cinco pela palavra "Buzz" e qualquer número divisível por três e cinco pela palavra "FizzBuzz".

A função `funq3` é um clássico exemplo de FizzBuzz implementado em Haskell. A ideia é retornar uma resposta dependendo do valor de `n`, e neste caso:

- Se `n` for múltiplo de 15, retorna `"FizzBuzz"`.
- Se `n` for múltiplo de 3, retorna `"Fizz"`.
- Se `n` for múltiplo de 5, retorna `"Buzz"`.
- Para qualquer outro valor, apenas devolve o número como uma `String`.

### Como a função `funq3` funciona

A função `funq3` usa guardas (os `|` no código) para verificar as condições:

```
funq3 :: Int -> String
funq3 n
    | mod n 15 == 0 = "FizzBuzz"
    | mod n 3  == 0 = "Fizz"
    | mod n 5  == 0 = "Buzz"
    | otherwise     = show n
```

#### Explicando passo a passo

- `mod n 15 == 0` → Se `n` for divisível por 15, retorna `"FizzBuzz"`.
- `mod n 3 == 0` → Se `n` for divisível por 3, mas não por 15, retorna `"Fizz"`.
- `mod n 5 == 0` → Se `n` for divisível por 5, mas não por 15, retorna `"Buzz"`.
- `otherwise` → Para qualquer outro caso, ele só mostra o número como uma `String`.

### Exemplo Prático

Ao executar `map funq3 [1,2,3,4,5]`, ele retorna:

```haskell
["1","2","Fizz","4","Buzz"]
```

#### O que acontece em cada valor:

- `1` não atende a nenhuma condição, então mostra `"1"`.
- `2` também, então mostra `"2"`.
- `3` é divisível por 3, então retorna `"Fizz"`.
- `4` nada de especial, então mostra `"4"`.
- `5` é divisível por 5, então retorna `"Buzz"`.
