# Enunciado
Rastros do Hackudão da Chatuba
O tráfico de drogas da caótica cidade do RJ tem se tornado cada vez mais evoluído, e dessa vez decidiram contratar um hacker mais conhecido como hackudão da chatuba. Porém, ele ainda é muito n00b e sempre deixa rastros por onde passa, inclusive as ferramentas que usa em seus trabalhos. Siga o fluxo da captura encontrada em https://www.dropbox.com/s/mx3dqxdtuym45q7/captura.pcap?dl=0 , e ache a senha Chuck Norrys.


![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/sn4p_c4t/imagem_hackud1.png)
## Ideia de Solução
abrindo o pacote
a1

1. tcp contains www.

a2,a3,a4

2. Video de youtube de som para video
a5


3. Extrair arquivos http
a6

4. Achamos um arquivo de som, Vamos verificar se conseguimos tirar algo de dentro desse som atraves da ferramenta indicada no pacote anterior (MMSSTV) para windows ou QSSTV para linux.
a7


5. Abrindo o sound.m4a com a ferramenta do passo 4, temos uma imagem que diz qual o tipo de criptografia foi utilizada (MEGAN35)
a8

6. Percorrendo-se os pacotes, também achamos algo relacionado à VOIP Calls.
a9

7. Ao abrirmos as chamadas VOIP, podemos ouvir um audio. Nele, algum indivíduo diz para olhar o cripto_wireless que há uma senha para o wpa, e deve estar no vídeo.
a10,a11


8. Ao se percorrer os pacotes, encontramos outra dica. Usar o rtmp2flv para extrair um vídeo flv.
a12,a13,a14, .. a19

9. No vídeo aparecerá um QRCODE. Leia o QRCode. Pode-se usar o https://zxing.org.
a20, a21


10. Lido o QRCode temos como resultado.Como sabemos o tipo de criptografia, podemos ir ao site crypo.com e fica fácil ver que a flag é: 
a22,a23

Dica: Você não precisa analisar outros arquivos .pcap, somente o do link acima.
 















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









