# Resultados e Discussões

A simulação computacional desenvolvida teve como objetivo processar um sinal representativo do mundo físico, solucionando o Problema Norteador proposto pela metodologia PBL: avaliar o comportamento temporal de um sensor real e garantir seu correto processamento por meio da análise de propriedades estruturais.

## Análise do Sinal Adquirido
O modelo computacional simulou a aquisição de dados de um sensor utilizado para diferenciar o escoamento de ar e líquido (água) no interior de um duto. O sinal bruto, $x[n]$, refletiu perfeitamente o cenário físico: nas amostras iniciais (escoamento de ar/tubulação vazia), observou-se uma amplitude próxima a zero, carregada de perturbações de alta frequência características de ruído térmico de instrumentação. Em seguida, com a transição para o estado líquido, o sinal sofreu uma elevação abrupta na amplitude média, mantendo, no entanto, oscilações causadas pela turbulência do fluxo e variações de leitura do próprio sensor.

Em seu estado original contínuo, as rápidas flutuações e eventuais anomalias da medição tornariam a tomada de decisão – como o acionamento de uma válvula atuadora – altamente instável. O processo de discretização permitiu mapear esse comportamento temporal de forma algorítmica.

## Avaliação do Sistema de Processamento

Para tratar o sinal ruidoso, aplicou-se um filtro de Média Móvel, um modelo clássico de equação de diferenças. Ao avaliarmos as propriedades estruturais desse sistema matemático em busca do processamento correto do sinal, inferimos que:

1. Causalidade: O filtro foi implementado de forma que o cálculo atual da média dependesse exclusivamente da amostra presente e de amostras passadas armazenadas em buffer. Isso garante que o sistema seja causal, uma condição sine qua non para algoritmos embarcados em microcontroladores que operam e tomam decisões em tempo real durante a passagem do fluido.

2. Memória: Devido ao buffer que armazena os últimos valores de leitura para compor a média, o sistema é classificado como dependente de memória.

3. Linearidade e Invariância no Tempo (LIT): A operação consiste estritamente em somas e multiplicações por constantes escalares, o que configura um sistema Linear e Invariante no Tempo. Essa propriedade simplifica enormemente a previsibilidade do comportamento do software, assegurando que o filtro responderá à presença da água com a mesma eficácia, não importando em qual instante de tempo essa mudança ocorra.

4. Estabilidade BIBO: Do ponto de vista de controle, o sistema mostrou-se absolutamente estável (BIBO). Como a média é uma combinação linear de valores finitos em uma janela restrita de observação, garante-se matematicamente que nenhum pico espúrio (uma bolha de ar na água, por exemplo) resultará em uma saída matemática infinita ou divergente, o que causaria um erro fatal no processador do equipamento.

## Conclusão da Simulação

O gráfico gerado comprova a eficácia da teoria. O sinal de saída, $y[n]$, demonstrou uma curva de transição muito mais suave, eliminando os transientes falsos decorrentes do ruído de alta frequência. O cálculo computacional da Energia do sinal (que apresentou um valor finito, característico de janelas de processamento limitadas) corroborou o embasamento teórico. Em suma, ao unir os conceitos de discretização matemática e a imposição de restrições de sistema (como causalidade e estabilidade), obteve-se sucesso no tratamento analítico de sinais advindos de sensores aplicados à automação de processos físicos.