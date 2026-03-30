# Resumo Teórico: Fundamentos de Sinais e Sistemas Discretos
A teoria de processamento digital de sinais estabelece a base matemática rigorosa necessária para que fenômenos físicos do mundo real sejam representados, analisados e manipulados por dispositivos computacionais. Conforme a literatura clássica de Oppenheim e Schafer, essa conversão da natureza analógica para o domínio digital exige uma compreensão profunda da natureza dos sinais e das estruturas matemáticas dos sistemas que os processam.

## 1. Sinais Contínuos e Discretos

Um sinal é descrito matematicamente como uma função de uma ou mais variáveis independentes.

- Sinais Contínuos: São definidos para um domínio contínuo no tempo, representados por $x(t)$, onde $t \in \mathbb{R}$. Esses sinais modelam a esmagadora maioria dos fenômenos físicos diretos, como a variação de temperatura ou a tensão elétrica em um circuito analógico.

-Sinais Discretos: São definidos apenas em instantes discretos de tempo, representados matematicamente como sequências $x[n]$, onde $n \in \mathbb{Z}$. Na prática da engenharia, essas sequências são frequentemente obtidas através da amostragem periódica de um sinal contínuo, tal que $x[n] = x(nT_s)$, sendo $T_s$ o período de amostragem.

## 2. Sequências Elementares
A análise de sistemas complexos é facilitada pela decomposição de sinais arbitrários em sequências fundamentais:

- Impulso Unitário (Amostra Unitária): Definido como $\delta[n] = 1$ para $n = 0$, e $\delta[n] = 0$ para $n \neq 0$. É a base para a representação de sistemas através da resposta ao impulso.

- Degrau Unitário: Definido como $u[n] = 1$ para $n \ge 0$, e $u[n] = 0$ para $n < 0$. É amplamente utilizado para modelar sinais que "ligam" em um instante específico.

- Exponenciais Complexas: Possuem a forma geral $x[n] = A \alpha^n$, onde $A$ e $\alpha$ podem ser números complexos. São autocomponentes de sistemas lineares e invariantes no tempo (LIT), sendo os alicerces da Transformada de Fourier e Transformada Z.

## 3. Operações com Sinais
O processamento em si ocorre através de manipulações algébricas elementares sobre a variável independente ou sobre a amplitude do sinal:

- Deslocamento no tempo: $x[n-k]$ representa um atraso (se $k > 0$) ou avanço (se $k < 0$) do sinal em $k$ amostras.

- Inversão temporal: $x[-n]$ espelha a sequência em torno do eixo vertical $n = 0$.

- Escalonamento: Pode ocorrer no tempo, através da decimação/interpolação, ou na amplitude, multiplicando a sequência por um ganho escalar.

## 4. Energia e Potência de Sinais

Segundo Proakis, a caracterização energética constitui uma etapa essencial no desenvolvimento de algoritmos de processamento digital.

- Energia ($E$): A energia total de uma sequência é dada por $E = \sum_{n=-\infty}^{\infty} |x[n]|^2$. Sinais com energia finita (e potência nula) são classificados como sinais de energia.

- Potência Média ($P$): Para sinais cuja energia tende ao infinito (como ruídos contínuos ou sinais periódicos), calcula-se a potência média ao longo de um intervalo infinito: $P = \lim_{N \to \infty} \frac{1}{2N+1} \sum_{n=-N}^{N} |x[n]|^2$. Sinais com potência finita e não-nula são sinais de potência.

## 5. Classificação de Sistemas Discretos
A modelagem de sistemas exige a identificação de propriedades que governam a relação matemática de transformação $y[n] = \mathcal{T}\{x[n]\}$. As principais classificações são:
- Sistemas com e sem memória: Um sistema é estático (sem memória) se $y[n]$ depender única e exclusivamente de $x[n]$ no mesmo instante $n$. Se a saída depender de valores passados ($x[n-1]$) ou futuros ($x[n+1]$), o sistema é dinâmico (com memória).
- Sistemas lineares e não lineares: Sistemas lineares obedecem ao Princípio da Superposição, que engloba a aditividade e a homogeneidade (escalonamento).
- Sistemas causais e não causais: A causalidade dita que a resposta em um instante $n$ não pode depender de instantes futuros de entrada ($x[n+k], k > 0$). Todos os sistemas processados em tempo real devem, obrigatoriamente, ser causais.
- Sistemas invariantes e variantes no tempo: A invariância no tempo garante que as características de processamento do sistema não mudam à medida que o tempo avança. Um atraso na entrada causa exatamente o mesmo atraso na saída.
- Estabilidade BIBO (Bounded-Input Bounded-Output): Um sistema é estável se qualquer entrada de amplitude limitada produzir uma resposta também limitada em amplitude ($|y[n]| \le M_y < \infty$).
- Invertibilidade: Ocorre quando o sistema apresenta uma relação biunívoca entre entrada e saída, permitindo a existência de um sistema inverso capaz de recuperar integralmente o sinal $x[n]$ a partir de $y[n]$.