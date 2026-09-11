# Roteiro 1

## Exercício 01

1. Link para a simulação: https://www.falstad.com/s.php?s=Qi46Et
2. Os resistores estão em paralelo, não em série, com a fonte de 5V. Logo, a tensão que passa pelos resistores será a mesma da fonte, 5V; já a corrente é calculada pela 1ª lei de Ohm, dada por $I = \frac{V}{R} = \frac{5V}{1000\Omega} = 5mA$. Ou seja, $V = 5V, I = 5mA$.
3. Ok.
4. O valor medido na simulação foi de exatamente 5mA, o que condiz com o cálculo encontrado na 2;
5. A corrente real não seria a mesma que a calculada, pois há fatores físicos que não são levados em consideração no cálculo teórico como a margem de erro dos resistores e a própria carga do amperímetro que produziriam leve interferência na medição.

## Exercício 02

1. Link para a simulação: https://www.falstad.com/s.php?s=wncGMp
2. Dado que a constante de tempo é dada pelo produto da resistência do circuito e a capacitância, temos $\tau = 220k\Omega \cdot 22uF = 220000 \cdot (22 \cdot 10^{-6}) = 4.84$ segundos. 
3. Ok
4. 
    a) O tempo calculado e o medido (aproximadamente 4.86 segundos) são muito próximos. A constante de tempo do circuito RC é o tempo que leva para carregar o capacitor de uma carga de 0% até 63,2%; como 63,2% de 3V corresponde a aproximadamente 1.9V, e na medição levou cerca de 4.86 segundos para atingir esse valor, sabemos que a equivalência entre os tempos está correta; 
    b) Dada a fórmula da constante do tempo, se diminuirmos qualquer grandeza necessariamente o resultado será diminuido. Assim, se diminuirmos a resistência, o tempo para a tensão atingir 1.9V também será menor.
5. Ao retornar a chave para a posição B ocorre o processo de descarregamento do capacitor até atingir a tensão de 0V. Esse é um processo gradual que ocorre pois não há mais alimentação de tensão, já que agora o circuito está fechado, resultando na dissipação de energia em forma de calor no meio.
