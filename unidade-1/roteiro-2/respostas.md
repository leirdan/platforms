# Roteiro 2

## Exercício 1

1. Link para a simulação: https://www.falstad.com/s.php?s=v1XUAI; como é possível visualizar, o LED está aceso.
2. A tensão aproximada no resistor de 1k é de 2.835V; isso ocorre pois o diodo está consumindo cerca de 0.5V, enquanto o LED consome 1.662V, restando ao resistor os 2.835V.
3. Dadas as informações, temos que, na teoria, o resistor consome de tensão $V = 5V - 0.7V - 1.7V = 2.6V$. Assim, na teoria, a corrente que passa através dele é de $I = \frac{2.6V}{1000\Omega} = 2.6mA$.
Na prática da simulação, foi possível constatar que a corrente medida que passa pelo resistor é de exatamente $2.835mA$, portanto, é um valor próximo ao calculado.
4. Link para a simulação: https://www.falstad.com/s.php?s=JgHjit. Neste caso, o LED permanece apagado.
5. No circuito 1, o diodo conduz corrente até o LED, pois esta atravessa o terminal ânodo/positivo do diodo; no circuito 2, porém, o diodo impede a passagem da corrente e mantém o LED apagado, pois esta atravessa agora o terminal cátodo/negativo do diodo.
6. Não houve diferença em relação ao item 5: o LED continua apagado. A razão disso se dá pelo fato do próprio LED ser um diodo que está recebendo corrente no terminal negativo, o que impede a passagem de corrente para o resto do circuito e não faz acendê-lo.
7. Link para a simulação: https://www.falstad.com/s.php?s=6imPwA. 
a) Pelas experimentações, o LED acende 1 vez a cada segundo, dentre os primeiros 500 milisegundos.
b) Durante esse período a tensão chega quase a 0V; isso ocorre pois, durante o semiciclo negativo, o diodo fica polarizado reversamente e bloqueia a corrente ao longo do restante do circuito.

## Exercício 2
1. Link para a simulação: https://www.falstad.com/s.php?s=03tllC
2. De acordo com a troca das chaves, a porta lógica que o circuito representa é o **OR**, pois basta somente 1 chave esteja no nível lógico 1 que o LED acende.
3. Link para a simulação: https://www.falstad.com/s.php?s=a03Gfd
4. De acordo com a troca das chaves, a porta lógica que o circuito representa é o **AND**, pois é necessário que as duas chaves estejam no nível lógico 1 para que o circuito conduza eletricidade e o LED acenda.