# PDS---Trabalho-01---Arthur-e-Gabriel
  Quando você liga para um serviço de atendimento automático e ouve instruções como "Para falar com o setor X, disque 3", é a tecnologia DTMF (Dual Tone Multi Frequency) que possibilita o reconhecimento do dígito que você pressionou. Esse sistema traduz as teclas pressionadas em frequências sonoras que são interpretadas pelo sistema de atendimento. Cada tecla do telefone produz um som composto por dois tons distintos, cada um com uma frequência específica que corresponde à linha e à coluna da matriz do teclado. Esse método de "dois tons, múltiplas frequências" permite que o sistema capte com precisão o som gerado e o associe ao número digitado.
  No código criado, simulamos a geração, avaliação e decodificação do sinal DTMF, algo parecido com o funcionamento de um sistema de atendimento. No código, ao produzir o som DTMF de um dígito único, utilizamos a Transformação Rápida de Fourier (FFT) para reconhecer as frequências predominantes no sinal. Essas frequências são associadas ao dígito corespondente.

Etapas do Processo:
  1. Configuração 
Bibliotecas Utilizadas: numpy, matplotlib, scipy.
Configuração das Frequências DTMF: O sistema DTMF utiliza duas séries de frequências, chamadas de frequências de linha (697 Hz, 770 Hz, 852 Hz, 941 Hz) e frequências de coluna (1209 Hz, 1336 Hz, 1477 Hz, 1633 Hz). Cada dígito do telefone corresponde a uma combinação única dessas frequências.
  
  2. Função de Geração do Sinal DTMF
 A função gerar_sinal_dtmf(digito, duracao, taxa_amostragem) recebe um dígito e combina as frequências de linha e coluna para gerar o sinal DTMF.
Exemplo: Para o dígito 5, as frequências combinadas são 770 Hz (linha) e 1336 Hz (coluna). O sinal gerado é uma combinação dessas duas frequências.

  3. Transformada Rápida de Fourier (FFT)
 Aplicamos a Transformada Rápida de Fourier ao sinal gerado para identificar as frequências dominantes.
Resultado: O espectro de frequências do sinal mostra picos nas frequências características do dígito escolhido (770 Hz e 1336 Hz no caso do 5).
Plot do Espectro de Frequências (FFT): O gráfico a seguir mostra o espectro do sinal DTMF para o dígito 5, com picos evidentes nas frequências dominantes.

 4. Detecção das Frequências Dominantes
 Utilizamos a função find_peaks para identificar os picos no espectro de frequências que correspondem às frequências de linha e coluna.
 
 5. Decodificação do Dígito
  A função decodificar_dtmf(frequencias) recebe as frequências dominantes detectadas e as compara com o mapeamento DTMF para identificar o dígito correspondente.

 6. Teste e Validação
 Teste Realizado: O programa foi testado com diferentes dígitos para verificar a precisão da detecção e decodificação.
Resultado: Em cada caso, as frequências detectadas foram mapeadas corretamente para o dígito DTMF correspondente.





