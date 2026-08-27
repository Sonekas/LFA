# Resoluções — Linguagens Formais e Autômatos

## Exercício 1

1. O alfabeto possui **3 símbolos**.
2. Os símbolos são $a$, $b$ e $c$.
3. **Verdadeiro:** $a\in\Sigma$.
4. **Falso:** $d\notin\Sigma$.
5. Um exemplo de palavra válida é `abc`. Também seriam válidas `a`, `ab`, `bca` e `cab`.

## Exercício 2

| Sequência | Classificação | Justificativa |
|---|---|---|
| `0101` | Palavra válida | Todos os símbolos pertencem a $\Sigma=\{0,1\}$. |
| `00110` | Palavra válida | Todos os símbolos pertencem ao alfabeto. |
| `012` | Não é palavra válida | O símbolo `2` não pertence a $\Sigma$. |
| `111` | Palavra válida | Todos os símbolos são `0` ou `1`. |
| `10a` | Não é palavra válida | O símbolo `a` não pertence a $\Sigma$. |

## Exercício 3

1. $0\in\Sigma$: **verdadeiro**, pois `0` é um símbolo do alfabeto.
2. $1\in\Sigma$: **verdadeiro**, pois `1` é um símbolo do alfabeto.
3. $01\in\Sigma$: **falso**, pois `01` é uma palavra com dois símbolos, e não um símbolo individual.
4. $01\in\Sigma^*$: **verdadeiro**, pois todos os símbolos de `01` pertencem ao alfabeto.
5. $2\in\Sigma$: **falso**, pois `2` não pertence ao alfabeto.
6. $101\in\Sigma^*$: **verdadeiro**, pois todos os símbolos de `101` pertencem a $\Sigma$.

## Exercício 4

| Palavra | Resultado |
|---|---|
| `0` | $0\in L$ |
| `01` | $01\in L$ |
| `0111` | $0111\in L$ |
| `10` | $10\notin L$ |
| `111` | $111\notin L$ |
| `011` | $011\in L$ |

## Exercício 5

1. As cinco primeiras palavras são:

   ```text
   b
   bb
   bbb
   bbbb
   bbbbb
   ```

2. $b^n$ representa uma palavra formada por $n$ ocorrências do símbolo `b`.
3. **Sim:** `bbbbbb` pertence à linguagem, pois `bbbbbb = b^6` e $6\geq1$.
4. **Não:** $\varepsilon\notin L$, pois a palavra vazia corresponde a $b^0$, mas a condição exige $n\geq1$.

## Exercício 6

- $L=\emptyset$ não possui nenhuma palavra.
- $L=\{\varepsilon\}$ possui exatamente uma palavra: $\varepsilon$.
- A palavra $\varepsilon$ possui comprimento zero: $|\varepsilon|=0$.
- Portanto, $\emptyset\neq\{\varepsilon\}$.

## Exercício 7

- Conjunto de variáveis: $V=\{S,A\}$.
- Conjunto de terminais: $T=\{0,1\}$.
- Conjunto de produções: $P=\{S\rightarrow0A,\ A\rightarrow1\}$.
- Símbolo inicial: $S$.
- Palavra gerada:

  $$
  S\Rightarrow0A\Rightarrow01
  $$

  Logo, a palavra gerada é `01`.

## Exercício 8

Aplicando $S\rightarrow0S$ sucessivamente:

- Uma vez: $S\Rightarrow0S$.
- Duas vezes: $S\Rightarrow0S\Rightarrow00S$.
- Três vezes: $S\Rightarrow0S\Rightarrow00S\Rightarrow000S$.

A sequência completa solicitada é:

$$
\boxed{S\Rightarrow0S\Rightarrow00S\Rightarrow000S}
$$

A derivação ainda não terminou, pois permanece o não terminal $S$.

## Exercício 9

Para gerar `aaab`, utilizamos $S\rightarrow aS$ três vezes e, depois, $S\rightarrow b$:

$$
\boxed{S\Rightarrow aS\Rightarrow aaS\Rightarrow aaaS\Rightarrow aaab}
$$

## Exercício 10

A gramática gera palavras formadas por zero ou mais `0` seguidos de um único `1`.

| Palavra | Pode ser gerada? | Derivação ou justificativa |
|---|---|---|
| `1` | Sim | $S\Rightarrow1$ |
| `01` | Sim | $S\Rightarrow0S\Rightarrow01$ |
| `001` | Sim | $S\Rightarrow0S\Rightarrow00S\Rightarrow001$ |
| `0001` | Sim | $S\Rightarrow0S\Rightarrow00S\Rightarrow000S\Rightarrow0001$ |
| `101` | Não | Após aplicar $S\rightarrow1$, a derivação termina; não é possível acrescentar outros símbolos. |
| `1001` | Não | A gramática exige que o `1` seja o último símbolo, mas essa palavra começa com `1` e possui símbolos depois dele. |

## Desafio final

A gramática gera palavras com zero ou mais `a`, terminadas por um único `b`.

1. `b` pode ser gerada:

   $$
   S\Rightarrow b
   $$

   Portanto, $b\in L(G)$.

2. `ab` pode ser gerada:

   $$
   S\Rightarrow aS\Rightarrow ab
   $$

   Portanto, $ab\in L(G)$.

3. `aab` pode ser gerada:

   $$
   S\Rightarrow aS\Rightarrow aaS\Rightarrow aab
   $$

   Portanto, $aab\in L(G)$.

4. `aaab` pode ser gerada:

   $$
   S\Rightarrow aS\Rightarrow aaS\Rightarrow aaaS\Rightarrow aaab
   $$

   Portanto, $aaab\in L(G)$.

5. `aba` **não** pode ser gerada. A produção $S\rightarrow b$ encerra a derivação; depois que `b` é produzido, não é possível acrescentar `a`.

   $$
   aba\notin L(G)
   $$

6. Derivação completa de `aaaab`:

   $$
   \boxed{S\Rightarrow aS\Rightarrow aaS\Rightarrow aaaS\Rightarrow aaaaS\Rightarrow aaaab}
   $$

7. O padrão da linguagem é:

   $$
   L(G)=\{a^n b\mid n\geq0\}
   $$

   Portanto, são geradas palavras como `b`, `ab`, `aab`, `aaab` e `aaaab`. A palavra vazia não pertence à linguagem, porque o símbolo `b` é obrigatório e sempre aparece no final.
