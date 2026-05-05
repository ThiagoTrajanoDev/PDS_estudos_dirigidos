# Atividade 6 – Análise de Estabilidade e Causalidade

Para cada sistema proposto, deve-se verificar duas propriedades fundamentais:

- **Causalidade:** o sistema é causal quando a saída em um instante $n$ depende apenas da entrada presente ou de entradas passadas.
- **Estabilidade:** o sistema é estável quando toda entrada limitada produz uma saída também limitada. Em sistemas LTI, isso equivale a verificar se a resposta ao impulso é absolutamente somável.

---

## a) $y[n] = x[n] + x[n-1]$

### Análise da causalidade

A saída no instante $n$ depende de:

- $x[n]$ → entrada atual;
- $x[n-1]$ → entrada passada.

Não há dependência de valores futuros da entrada.

Portanto, o sistema é **causal**.

---

### Análise da estabilidade

Se a entrada for limitada, isto é, seus valores não ultrapassarem certo limite, então:

- $x[n]$ é limitado;
- $x[n-1]$ também é limitado.

A soma de dois valores limitados continua sendo limitada.

Logo, a saída também permanecerá limitada.

Assim, o sistema é **estável**.

---

## b) $y[n] = x[n+1]$

### Análise da causalidade

Neste caso, a saída em $n$ depende de:

$$
x[n+1]
$$

ou seja, depende de uma amostra futura da entrada.

Isso significa que para calcular a saída atual seria necessário conhecer um valor que ainda não ocorreu.

Portanto, o sistema é **não causal**.

---

### Análise da estabilidade

Apesar de não ser causal, se a entrada for limitada, então o valor futuro $x[n+1]$ também será limitado.

Como a saída é apenas uma cópia deslocada da entrada, ela não crescerá indefinidamente.

Logo, o sistema pode ser considerado **estável**.

---

## c) $h[n] = (0.5)^n u[n]$

Aqui foi fornecida diretamente a resposta ao impulso do sistema.

A presença de $u[n]$ (degrau unitário) indica que:

$$
h[n] = 0 \quad para \quad n < 0
$$

e

$$
h[n] = (0.5)^n \quad para \quad n \geq 0
$$

---

### Análise da causalidade

Como a resposta ao impulso é nula para todos os instantes negativos, o sistema não responde antes da aplicação da entrada.

Isso satisfaz a condição de causalidade de sistemas LTI.

Portanto, o sistema é **causal**.

---

### Análise da estabilidade

Os valores da sequência são:

$$
1,\ 0.5,\ 0.25,\ 0.125,\dots
$$

Percebe-se que a sequência decresce rapidamente e tende a zero.

A soma absoluta é:

$$
1 + 0.5 + 0.25 + 0.125 + \dots
$$

Trata-se de uma progressão geométrica convergente com razão $0.5$.

Como essa soma é finita, a resposta ao impulso é absolutamente somável.

Assim, o sistema é **estável**.

---

## d) $h[n] = 2^n u[n]$

Novamente:

$$
h[n] = 0 \quad para \quad n < 0
$$

e

$$
h[n] = 2^n \quad para \quad n \geq 0
$$

---

### Análise da causalidade

Como a resposta ao impulso é nula antes de $n=0$, o sistema não antecipa a entrada.

Logo, o sistema é **causal**.

---

### Análise da estabilidade

Os valores da resposta ao impulso são:

$$
1,\ 2,\ 4,\ 8,\ 16,\dots
$$

Nesse caso a sequência cresce indefinidamente.

A soma absoluta:

$$
1 + 2 + 4 + 8 + \dots
$$

não converge, pois trata-se de uma progressão geométrica divergente com razão maior que 1.

Isso significa que pequenas entradas podem gerar saídas muito grandes.

Portanto, o sistema é **instável**.

---

## Resumo Final

### a) $y[n] = x[n] + x[n-1]$

- Causal: **sim**
- Estável: **sim**

---

### b) $y[n] = x[n+1]$

- Causal: **não**
- Estável: **sim**

---

### c) $h[n] = (0.5)^n u[n]$

- Causal: **sim**
- Estável: **sim**

---

### d) $h[n] = 2^n u[n]$

- Causal: **sim**
- Estável: **não**

---

## Conclusão

A análise mostra que causalidade está relacionada à dependência temporal da saída em relação à entrada, enquanto estabilidade está associada ao comportamento limitado da resposta do sistema.

Um sistema pode ser estável sem ser causal, como no item (b), e também pode ser causal mas instável, como no item (d). Portanto, são propriedades distintas e devem sempre ser verificadas separadamente.