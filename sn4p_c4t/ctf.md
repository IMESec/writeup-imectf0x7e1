# Enunciado
Uma funcionária de uma empresa estava armazenando seus arquivos pessoais em um computador de trabalho. Infelizmente, ele corrompeu o sistema de arquivos antes que pudéssemos prová-lo. Você pode dar uma olhada? Link para baixar o arquivo: https://drive.google.com/open?id=0B_8nyUDljo0ycWthazJZRFR4NkE

## Ideia de Solução
Analisando-se o arquivo atraves do comando strings, obtemos algumas linhas que indicam que há imagens JPG dentro do arquivo.
![Alt text](/writeup-imectf0x7e1/sn4p_c4t/Captura de Tela 2017-05-16 às 18.07.33.png?raw=true)

Podemos analisar o arquivo atraves do hexdump, e procurar pela assinatura de arquivos JPG através do site http://www.garykessler.net/library/file_sigs.html . Confirmamos então que há vários arquivos jpg.


Com o hexdump conseguimos verificar que há várias sequências que começam com FF D8 e terminam com FF D9 ( assinatura de um arquivo JPG ). Então, sabemos que trata-se de um arquivo que contém imagens. 

MAs como extraí-lo? Simples, copie a parte compreendida entre FF D8 e FF D9 para um arquivo novo no editor hexadecimal e salve. Pronto, só abrir com um editor de texto.Assim, encontramos a flag. 
Já sei que você vai me falar que existe uma ferramenta chamada foremost que facilite isso tudo. Pois é, você está parcialmente certo. O foremost extrai os principais tipos de arquivos, porém e se o arquivo que quero extrair não é o usual? Você saberia? Agora espero que sim :)
