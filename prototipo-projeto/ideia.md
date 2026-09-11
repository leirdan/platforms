# Dispositivo de detecção de adulteração do mel no Seridó com ESP32 e componentes de baixo custo

## Descrição 

Este projeto consiste em um sistema de controle de qualidade de lotes de méis. Neste sistema teremos a utilização de um S.E. para a leitura e detecção de qualidade das amostras unido com uma aplicação web capaz de produzir relatórios e gráficos a partir dos dados coletados. As entradas deste sistema serão $n$ amostras de um mesmo lote de mel, enquanto a saída de cada amostra consistirá na seguinte classificação: “Positivo” para amostras adulteradas, “Negativo” para amostras não adulteradas e “Indefinido” para resultados imprecisos ou fora do padrão. Estas saídas serão enviadas à aplicação web para o armazenamento e produção de relatórios a posteriori.

## Componentes 

- Plataforma: microcontrolador ESP32;
- Linguagens de Programação: C (ESP32), Python (script de geração de relatórios);
- Protocolos de comunicação: MQTT, HTTP;
- Atuadores: N/A;
- Sensores: pH, umidade, condutividade elétrica e densidade;
- Outros: broker MQTT (Mosquitto), Adafruit IO;

## Especificação
### Objeto de estudo
O mel é uma substância composta por 80% de carboidratos, 18% de água e 2% de proteínas, tendo também pH menor que 7 (para méis florais, e.g., varia entre 3.3 e 4.6).

Alguns métodos comuns para avaliar a qualidade do mel são:
1) medição da permissividade: através da passagem de corrente elétrica pode-se medir facilmente méis que tiveram água acrescentada;
2) cromatografia: separação de componentes de misturas para medir glicose, frutose e sacarose, ideal para detectar xaropes;
3) espectroscopia: com o método FTIR é possível detectar padrões de vibração molecular da amostra e comparar com valores de referência de meis;
4) refratometria: calculando o índice de refração da amostra, é possível comparar também com valores de referência e determinar pureza.

Vários métodos prezam pela união com modelos de Machine Learning, como a espectroscopia. Entretanto, pelo escopo do projeto e prazo da disciplina, serão utilizados somente componentes elétricos; essa decisão é baseada no seguinte estudo sobre detecção de adulteração no leite, que foi feita utilizando somente componentes eletrônicos: https://www.academia.edu/44315339/IRJET_ADULTERATION_DETECTION_IN_MILK_USING_EMBEDDED_SYSTEM

De modo geral, uma forma de avaliar a qualidade do mel poderia ser uma combinação de sensores e atuadores ao invés de 1 único método, como:
- Sensor para medir a condutividade elétrica da amostra;
- Sensor de pH para determinar o nível de acidez do mel;
- Sensor de umidade que avalie a presença de água;
- Sensor de densidade que avalie a viscosidade e volume;
- Sensor de refratometria e/ou técnica de espectroscopia com FITR.

Como os sensores de refratometria/espectroscopia são bastante caros, serão utilizados somente os 4 primeiros sensores citados, possibilitando determinar de forma rápida e inicial se o mel está ou não adulterado com alguma substância. Não será o objetivo da aplicação determinar qual o tipo de adulteração, somente retornar "Positivo", "Negativo" ou "Indefinido".

### Medição
A estratégia consiste em combinar estes 4 sensores para a coleta de dados e fazer comparações de cada dado com valores de referência do mel típico da região Seridó. Com a combinação dos sensores de diferentes propriedades físicas teremos maior segurança na resposta; e.g., o pH do mel pode estar fora do intervalo esperado mas os outros parâmetros normais, o que pode não caracterizar um mel como adulterado. Para armazenar a amostra será utilizada uma caixa de acrílico com os sensores acoplados em suas paredes. Assim, ao colocar a amostra e ligar o dispositivo, os sensores farão a captura automatizada das informações e enviarão à aplicação web via protocolo MQTT.

### Visualização de dados
Para visualizar os resultados das análises, contaremos com a aplicação web Adafruit IO. O Adafruit no plano básico provê o uso de dashboards, uma ótima forma de monitoramento. Contudo, para geração de relatórios, será elaborado um script em Python para consulta à API do Adafruit e criação de um PDF com os dados coletados até o momento. Neste PDF deverão estar ao menos as seguintes variáveis: quantidade de amostras analisadas, percentual de adulteração e de amostras indefinidas por produtor e média de pH, umidade, densidade e condutividade elétrica das últimas 50 amostras. Vale notar que o Adafruit guarda os dados por até 30 dias em seu servidor, logo, o uso deste script deve ser feito de forma diária para não haver perda de informações.

## Entrega

A entrega final do projeto consistirá na prototipagem física de um circuito que integre o microcontrolador e sensores ao dispositivo de acrílico para medição do mel e do script em Python para gerar o relatório. Durante a demonstração, serão utilizadas amostras reais de mel para testagem, onde será possível detectar a qualidade de cada amostra, enviar para o Adafruit e, logo em seguida, gerar o relatório da demonstração.

## Artigos de referência:
- Informações sobre mel: https://www.researchgate.net/publication/348551159_CORRELACAO_DAS_PROPRIEDADES_DE_CONDUTIVIDADE_ELETRICA_pH_e_ANALISE_MELISSOPALINOLOGICA_DO_MEL_DO_VALE_DO_RIBEIRA_SAO_PAULO_BRASIL
- Detecção de adulteração em leite com FTIR: https://editora.editoraomnisscientia.com.br/artigoPDF/24212095490.pdf
- Detecção de adulteração de mel com espectroscopia Vis-NIR e ML: https://www.mdpi.com/2304-8158/12/13/2491
- Detecção de adulteração de mel com sensor de gás e ML: https://www.nature.com/articles/s41538-025-00440-9
