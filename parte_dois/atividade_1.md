# Atividade 1 – Interpretação Conceitual

#### 1) O que significa afirmar que um sistema é linear e invariante no tempo?

Dizer que um sistema é **linear** significa que ele obedece ao princípio da superposição, isto é, se uma entrada produz uma determinada saída e outra entrada produz outra saída, então a soma dessas entradas produzirá a soma correspondente das saídas. Além disso, se a entrada for multiplicada por uma constante, a saída também será multiplicada por essa mesma constante.

Já afirmar que o sistema é **invariante no tempo** significa que seu comportamento não muda com o passar do tempo. Em outras palavras, se um sinal de entrada for aplicado hoje ou em qualquer outro instante, a forma como o sistema responde será a mesma, apenas deslocada no tempo.

Assim, um sistema LTI (Linear e Invariante no Tempo) possui comportamento previsível e matematicamente tratável.


#### 2) Por que a resposta ao impulso é suficiente para caracterizar um sistema LTI?

A resposta ao impulso é suficiente porque qualquer sinal discreto pode ser representado como uma soma de impulsos deslocados e ponderados. Como o sistema é linear, ele responde à soma dos impulsos como a soma das respostas individuais. Como ele é invariante no tempo, basta conhecer a resposta a um impulso em um instante de referência, pois as demais respostas serão apenas versões deslocadas.

Desse modo, conhecendo-se a resposta ao impulso, é possível determinar a saída do sistema para qualquer entrada através da operação de convolução. Por isso, a resposta ao impulso funciona como uma “assinatura” completa do sistema LTI.


#### 3) Qual o significado físico da convolução em sistemas discretos?

Fisicamente, a convolução representa o processo de construção da saída total de um sistema a partir da contribuição de cada amostra da entrada. Cada valor da entrada pode ser visto como um pequeno estímulo aplicado ao sistema, e esse estímulo gera uma resposta proporcional à resposta ao impulso.

A saída final é obtida somando todas essas pequenas respostas, considerando seus deslocamentos no tempo. Portanto, a convolução mostra como o sistema “acumula” os efeitos passados da entrada para produzir a resposta atual.

Em termos práticos, ela descreve a memória do sistema e a influência que valores anteriores da entrada exercem sobre a saída.


#### 4) Qual a diferença entre resposta transitória e regime permanente?

A **resposta transitória** é a parte inicial da saída do sistema, observada logo após a aplicação de uma entrada ou de uma perturbação. Nessa fase, o sistema ainda está se ajustando às novas condições e podem ocorrer oscilações, crescimentos ou decaimentos.

Já o **regime permanente** é a parte da resposta em que o comportamento do sistema se estabiliza. Após o desaparecimento dos efeitos transitórios, a saída passa a seguir um padrão mais constante ou periódico, dependendo da entrada aplicada.

Assim, a resposta transitória está associada à adaptação inicial, enquanto o regime permanente representa o comportamento duradouro do sistema.



#### 5) O que se entende por sistema causal?

Um sistema causal é aquele cuja saída em um determinado instante depende apenas dos valores presentes e passados da entrada, nunca de valores futuros.

Isso significa que o sistema não precisa “adivinhar” o que ainda vai acontecer para gerar sua resposta. Essa característica é fundamental em sistemas físicos reais, pois no mundo prático não é possível utilizar informações que ainda não ocorreram.

Portanto, causalidade está diretamente relacionada à viabilidade de implementação do sistema em tempo real.


#### 6) O que se entende por sistema estável?

Um sistema estável é aquele que produz uma saída limitada sempre que recebe uma entrada limitada. Em outras palavras, se o sinal de entrada não cresce indefinidamente, a saída também não deve crescer sem controle.

Fisicamente, isso significa que o sistema responde de maneira controlada, sem explodir ou apresentar comportamentos divergentes.

Nos sistemas LTI discretos, essa estabilidade está relacionada ao fato de que a soma absoluta da resposta ao impulso deve ser finita. Se essa condição for satisfeita, o sistema é considerado estável e confiável para operação.