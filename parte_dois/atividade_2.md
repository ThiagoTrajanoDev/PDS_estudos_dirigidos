# Atividade 2 – Cálculo Manual de Convolução

Considere as sequências discretas:

- $x[n] = \{1, 2, 1\}$
- $h[n] = \{1, 1\}$

Deseja-se calcular:

$$
y[n] = x[n] * h[n]
$$

onde $*$ representa a operação de convolução discreta.

---

## 1) Cálculo manual da convolução $y[n] = x[n] * h[n]$

A fórmula geral da convolução discreta é:

$$
y[n] = \sum_{k=-\infty}^{\infty} x[k] \, h[n-k]
$$

Como as sequências possuem tamanho finito, calculamos valor por valor.

### Para $n = 0$

$$
y[0] = x[0]h[0]
$$

$$
y[0] = 1 \cdot 1 = 1
$$

---

### Para $n = 1$

$$
y[1] = x[0]h[1] + x[1]h[0]
$$

$$
y[1] = 1 \cdot 1 + 2 \cdot 1 = 3
$$

---

### Para $n = 2$

$$
y[2] = x[1]h[1] + x[2]h[0]
$$

$$
y[2] = 2 \cdot 1 + 1 \cdot 1 = 3
$$

---

### Para $n = 3$

$$
y[3] = x[2]h[1]
$$

$$
y[3] = 1 \cdot 1 = 1
$$

---

## 2) Resultado em forma de sequência

Portanto:

$$
y[n] = \{1, 3, 3, 1\}
$$

---

## 3) Explicação do significado do resultado

A convolução mostra como o sistema representado por $h[n]$ atua sobre o sinal de entrada $x[n]$.

Como $h[n] = \{1,1\}$, isso significa que o sistema soma cada amostra atual da entrada com a amostra vizinha anterior ou posterior durante o processo de sobreposição.

Por isso:

- o primeiro elemento resulta apenas de uma multiplicação;
- os elementos centrais recebem contribuição de duas posições e ficam maiores;
- o último elemento volta a ter apenas uma contribuição.

Na prática, o sistema espalha a energia da sequência de entrada e produz uma espécie de soma acumulada entre amostras adjacentes.

Assim, a sequência original $\{1,2,1\}$ é transformada em $\{1,3,3,1\}$, evidenciando o efeito de memória do sistema e a construção gradual da saída pela convolução.