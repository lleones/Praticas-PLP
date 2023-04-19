# Pratica Funcional 2

Paulo foi em uma padaria e quer saber o valor da sua conta. Para ajudá-lo, faça um programa que receba a quantidade de itens consumidos, uma descrição dos itens e retorna o valor da conta.

Cardápio:

- cafe R$ 4
- pao R$ 2
- suco R$ 5
- pao de queijo R$ 5
- sanduiche R$ 3

**Teste Público:**

- Entrada:

5

cafe

pao

suco

cafe

sanduiche

- Saída:

18

```haskell
lanchonete::Int -> Int -> IO Int
lanchonete 0 total = return total
lanchonete x total = do
    input <- getLine
    let valor = somaConta input
    lanchonete (x-1) (total + valor)

somaConta::String->Int
somaConta x 
    |x == "cafe" = 4
    |x == "pao" = 2
    |x == "suco" = 5
    |x == "pao de queijo" = 5
    |x == "sanduiche" = 3
    |otherwise = 0
    
main::IO()
main = do
    input <- readLn
    total <- lanchonete input 0
    print(total)
```