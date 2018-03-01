# PreOrderBinaryTree

O código apresenta uma árvore binária do tipo *PreOrder*, caracteriza-se por começar a busca pelo nó central(Root),
seguido de seus filhos dos ramos em sua esquerda e finalmente os ramos em sua direita. 

# Objetivo

O objetivo era criar uma árvore binária, recursiva e usando o conceito de pilha, para estudos e futuras aplicações no meio de Inteligencia Artificial.

# Como funciona

A árvore apresentada tem como função determinar o valor de seus nós - até o nó principal - em True ou False. Para isso, baseia-se em parte da tabela verdade usando somente as operações de conjunção(AND(ˆ)) ou disjunção(OR(v)):


| A | B | AˆB |
|---|---|-----|
| V | V |  V  |
| V | F |  F  |
| F | V |  F  |
| F | F |  F  |

| A | B | AvB |
|---|---|-----|
| V | V |  V  |
| V | F |  V  |
| F | V |  V  |
| F | F |  F  |

# Author

* Mikael Schirru

