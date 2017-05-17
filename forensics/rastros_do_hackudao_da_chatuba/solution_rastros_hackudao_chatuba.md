# Enunciado
Rastros do Hackudão da Chatuba
O tráfico de drogas da caótica cidade do RJ tem se tornado cada vez mais evoluído, e dessa vez decidiram contratar um hacker mais conhecido como hackudão da chatuba. Porém, ele ainda é muito n00b e sempre deixa rastros por onde passa, inclusive as ferramentas que usa em seus trabalhos. Siga o fluxo da captura encontrada em https://www.dropbox.com/s/mx3dqxdtuym45q7/captura.pcap?dl=0 , e ache a senha Chuck Norrys.

### Dica: 
Você não precisa analisar outros arquivos .pcap, somente o do link acima.

## Ideia de Solução
abrindo o pacote
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a1.png)

1. tcp contains www.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a2.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a3.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a4.png)

2. Video de youtube de som para video
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a5.png)

3. Extrair arquivos http
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a6.png)

4. Achamos um arquivo de som, Vamos verificar se conseguimos tirar algo de dentro desse som atraves da ferramenta indicada no pacote anterior (MMSSTV) para windows ou QSSTV para linux.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a7.png)

5. Abrindo o sound.m4a com a ferramenta do passo 4, temos uma imagem que diz qual o tipo de criptografia foi utilizada (MEGAN35)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a8.png)

6. Percorrendo-se os pacotes, também achamos algo relacionado à VOIP Calls.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a9.png)

7. Ao abrirmos as chamadas VOIP, podemos ouvir um audio. Nele, algum indivíduo diz para olhar o cripto_wireless que há uma senha para o wpa, e deve estar no vídeo.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a10.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a11.png)

8. Ao se percorrer os pacotes, encontramos outra dica. Usar o rtmp2flv para extrair um vídeo flv.
a12,a13,a14, .. a19
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a12.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a13.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a14.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a15.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a16.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a17.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a18.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a19.png)

9. No vídeo aparecerá um QRCODE. Leia o QRCode. Pode-se usar o https://zxing.org.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a20.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a21.png)

10. Lido o QRCode temos como resultado.Como sabemos o tipo de criptografia, podemos ir ao site crypo.com e fica fácil ver que a flag é: 
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a22.png)
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/forensics/rastros_do_hackudao_da_chatuba/a23.png)

 















QRCode
# Para achar qual criptografia usar
youtube.com/watch?v=VrEapa4nL8o
Decripte com Megan-35
Dar uma olhada no crypto wireless 
Senha pro WPA
Deve estar no video

# Para baixar o video...
SIga o fluxo do stream rtmp
rtmp2flv
github.com/quo/rtmp2fly
video -> flv
qr code
le
decripta com megan-35
so_chuck_norrys_quebra

extense http
crypto_wireless 

wpa_passphrase Wireless 
pra gerar senha pra quebrar o arquivo
Coloca-lo no wireshark em edit-Preferences. Protocolo - IEEE802.11 + wpa-psk - key

OdNthsesSIG4huS4ngS7huyqm+NrOdNuhxKvRwOsbHesRfC1RZe5
#_$0h_Chuck_N0rr1$_qu3br@!_%









