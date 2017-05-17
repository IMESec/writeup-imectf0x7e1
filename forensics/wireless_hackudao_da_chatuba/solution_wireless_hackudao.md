# Enunciado
Wireless do Hackudão da Chatuba
Caso você tiver conseguido analisar a captura de rastros do Hackudão da Chatuba, o que você achou nessa parte te dá acesso a outra captura. Ache essa captura e quebre-a para achar a flag que te da acesso ao wifi do hackudão e ganhar 40 pontos extras :) . Link: https://www.dropbox.com/s/mx3dqxdtuym45q7/captura.pcap?dl=0
Dica: Parece ser bizu a ferramenta wpa_passphrase.

### Criador da Flag 
Cap Pedro Henrique - CdCiber

## Ideia de Solução
Dado que você já sabe a senha #_$0h_Chuck_N0rr1$_qu3br@!_% , queremos 
Agora abriremos o crypto_wireless e vemos que o SSID é Wireless
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b1.png)

Usamos wpa_passphrase para gerar a senha pra quebrar o arquivo 
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b2.png)

PAra acrescentar a chave, Vá às preferencias do Wireshark.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b3.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b4.png)

Protocolo IEE802.11, Edit.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b5.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b6.png)

Escolha wpa=psk e insire o passphrase. Clique em okay e o arquivo foi decriptografado.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b7.png)

PRocurando a flag por tcp contains flag, achamos: 
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/wireless_hackudao_da_chatuba/b8.png)

