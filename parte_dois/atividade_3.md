# Atividade 3 – Sistema Descrito por Equação de Diferenças

Considere o sistema discreto:

$$
y[n] = 0.8\,y[n-1] + x[n]
$$

admitindo:

- condição inicial nula: $y[-1] = 0$
- entrada impulso: $x[n] = \delta[n]$

Como a entrada é um impulso unitário, a saída obtida será justamente a **resposta ao impulso** do sistema, isto é:

$$
h[n] = y[n]
$$

---

## 1) Determinação dos primeiros valores de $h[n]$ para $0 \leq n \leq 5$

Sabemos que o impulso discreto possui os seguintes valores:

- $\delta[0] = 1$
- $\delta[n] = 0$ para $n \neq 0$

Agora substituímos sucessivamente na equação.

---

### Para $n = 0$

$$
y[0] = 0.8\,y[-1] + x[0]
$$

Como $y[-1] = 0$ e $x[0] = 1$:

$$
y[0] = 0.8 \cdot 0 + 1 = 1
$$

Logo:

$$
h[0] = 1
$$

---

### Para $n = 1$

$$
y[1] = 0.8\,y[0] + x[1]
$$

Como $x[1] = 0$:

$$
y[1] = 0.8 \cdot 1 = 0.8
$$

Logo:

$$
h[1] = 0.8
$$

---

### Para $n = 2$

$$
y[2] = 0.8\,y[1] + x[2]
$$

$$
y[2] = 0.8 \cdot 0.8 = 0.64
$$

Logo:

$$
h[2] = 0.64
$$

---

### Para $n = 3$

$$
y[3] = 0.8\,y[2]
$$

$$
y[3] = 0.8 \cdot 0.64 = 0.512
$$

Logo:

$$
h[3] = 0.512
$$

---

### Para $n = 4$

$$
y[4] = 0.8\,y[3]
$$

$$
y[4] = 0.8 \cdot 0.512 = 0.4096
$$

Logo:

$$
h[4] = 0.4096
$$

---

### Para $n = 5$

$$
y[5] = 0.8\,y[4]
$$

$$
y[5] = 0.8 \cdot 0.4096 = 0.32768
$$

Logo:

$$
h[5] = 0.32768
$$

---

### Sequência obtida

Portanto, os primeiros valores da resposta ao impulso são:

$$
h[n] = \{1,\ 0.8,\ 0.64,\ 0.512,\ 0.4096,\ 0.32768\}
$$

Percebe-se que a resposta forma uma progressão geométrica decrescente.

---

## 2) Discussão sobre a estabilidade do sistema

Um sistema LTI discreto é considerado estável quando sua resposta ao impulso é absolutamente somável, ou seja, quando seus valores não crescem indefinidamente e tendem a zero com o passar do tempo.

Observando a sequência obtida:

$$
1,\ 0.8,\ 0.64,\ 0.512,\dots
$$

nota-se que cada termo é 80% do termo anterior. Isso significa que a resposta vai diminuindo gradualmente e se aproxima de zero quando $n$ cresce.

Como a saída não diverge e os valores permanecem limitados, conclui-se que o sistema apresenta comportamento estável.

Além disso, como $|0.8| < 1$, a realimentação não amplifica o sinal, mas o atenua progressivamente.

---

## 3) Verificação da causalidade do sistema

Um sistema é causal quando a saída no instante $n$ depende apenas de:

- entradas presentes,
- entradas passadas,
- saídas passadas.

A equação fornecida é:

$$
y[n] = 0.8\,y[n-1] + x[n]
$$

Observe que:

- $y[n-1]$ é uma saída passada;
- $x[n]$ é a entrada presente.

Não aparece nenhum termo como $x[n+1]$ ou $y[n+1]$, que representariam dependência de valores futuros.

Portanto, a saída em cada instante pode ser calculada utilizando apenas informações já disponíveis naquele momento.

Assim, conclui-se que o sistema é **causal**.

---

## Conclusão

A resposta ao impulso calculada mostra que o sistema gera uma sequência decrescente:

$$
\{1,\ 0.8,\ 0.64,\ 0.512,\ 0.4096,\ 0.32768\}
$$

Essa sequência tende a zero, indicando que o sistema é estável. Além disso, como a equação depende somente da entrada atual e da saída passada, o sistema também é causal.