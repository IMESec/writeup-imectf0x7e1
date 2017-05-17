# Enunciado
Wireless do Hackudão da Chatuba
Caso você tiver conseguido analisar a captura de rastros do Hackudão da Chatuba, o que você achou nessa parte te dá acesso a outra captura. Ache essa captura e quebre-a para achar a flag que te da acesso ao wifi do hackudão e ganhar 40 pontos extras :) . Link: https://www.dropbox.com/s/mx3dqxdtuym45q7/captura.pcap?dl=0
Dica: Parece ser bizu a ferramenta wpa_passphrase.


![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/sn4p_c4t/imagem_hackud1.png)

## Ideia de Solução
Dado que você já sabe a senha #_$0h_Chuck_N0rr1$_qu3br@!_% , queremos 
Agora abriremos o crypto_wireless e vemos que o SSID é Wireless
b1

Usamos wpa_passphrase para gerar a senha pra quebrar o arquivo 
b2

PAra acrescentar a chave, Vá às preferencias do Wireshark.
b3,b4

Protocolo IEE802.11, Edit.
 b5,b6 

Escolha wpa=psk e insire o passphrase. Clique em okay e o arquivo foi decriptografado.
b7

PRocurando a flag por tcp contains flag, achamos: 
b8

