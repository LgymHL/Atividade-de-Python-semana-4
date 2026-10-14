# Sistema de Cadastro e Análise de Produtos

Desafio Sprint 4 — Desenvolvimento em Python (Listas, Tuplas e Conjuntos)

## Sobre o projeto
Sistema de cadastro e análise de produtos, entregue em duas versões
equivalentes: uma em **Python**, usando as estruturas de dados nativas
da linguagem, e outra em **Portugol**, reproduzindo a mesma lógica com
vetores de tamanho fixo e laços — já que Portugol não tem listas
dinâmicas, `sort()`/`sorted()` nem `set()` prontos.

As duas versões implementam as mesmas seis funcionalidades: cadastro de
produtos, filtragem por preço, ordenação crescente e decrescente,
conjunto de categorias únicas, tupla de estatísticas e relatório final
formatado.

## Estrutura dos arquivos

- **`produtos.py`** — versão em Python. Cadastro com `input()`/`append()`,
  filtragem por preço, ordenação com `sort()` (in-place) e
  `sorted(reverse=True)` (nova lista), conjunto de categorias com `{}` e
  tupla de estatísticas (menor, maior e média), tudo reunido num menu
  interativo que gera o relatório final com f-strings.
- **`produtos_portugol.por`** — versão em Portugol. A mesma lógica, mas
  com vetores de tamanho fixo no lugar das listas, laços `para` para
  percorrer e preencher os dados, **bubble sort manual** (com troca
  sincronizada dos três vetores paralelos — nome, preço e categoria) no
  lugar de `sort()`, e uma **simulação manual de conjunto** — comparando
  cada categoria com as já guardadas e ignorando as repetidas — no
  lugar de `set()`.

## Por que duas versões
O objetivo do desafio é mostrar que a lógica por trás de uma estrutura
de dados independe da sintaxe da linguagem. O Python resolve cadastro,
ordenação e remoção de duplicatas com métodos prontos (`append()`,
`sort()`, `set()`); a versão em Portugol reconstrói esse mesmo
comportamento "na mão", deixando explícito o que esses métodos fazem
por baixo dos panos.

## Correspondência entre as versões

| Funcionalidade | Em Python | Em Portugol |
|---|---|---|
| Armazenar produtos | Lista de tuplas + `append()` | Três vetores paralelos de tamanho fixo |
| Filtrar por preço | List comprehension (`if p[1] > valor`) | Laço `para` com `se` |
| Ordenar crescente | `produtos.sort()` | Bubble sort manual |
| Ordenar decrescente | `sorted(produtos, reverse=True)` | Bubble sort manual com a comparação invertida |
| Categorias únicas | `set()` por compreensão | Vetor auxiliar + busca linear para ignorar repetidas |
| Estatísticas | Tupla `(menor, maior, media)` | Três variáveis separadas (`menor_preco`, `maior_preco`, `media`) |
| Relatório final | f-strings | `escreva()` concatenando os resultados |

## Como executar

```bash
python produtos.py
```

A versão em Portugol (`produtos_portugol.por`) pode ser aberta e
executada no [VisualG](http://lite.acad.univali.br/portugol) ou em
qualquer interpretador compatível com a sintaxe Portugol.