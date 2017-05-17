# Enunciado
Você consegue encontrar a imagem (JPEG) entre milhares de arquivos? Link para baixar o arquivo: https://drive.google.com/open?id=0B_8nyUDljo0yeDAwVk5NM0NTOHM

Dica: Tente encontrar padrões.

## Ideia de Solução
Descompactar com unzip data.zip
Ao abrir o diretório, vemos muitos diretórios. 
Analisando-se os tamanhos de cada um, podemos verificar que há muitos diretórios de tamanho 0 e 26136.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/sn4p_c4t/imagem_palavras1.png)


Podemos verificar os diretórios que não seguem esse padrão.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/sn4p_c4t/imagem2.png)


Vemos que maybe117 é o único com esse tamanho. vamos abrir esse diretório para verificar.
Ao se listar o diretório, pode-se verificar que um arquivo está com cor diferente, pois tem permissão diferente dos outros. 
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/sn4p_c4t/imagem3.png)


Podemos analisar de outra maneira também. Como sabemos que é um arquivo JPEG, verificamos o formato de todos os arquivos pelo comando file e filtramos somente os que tem extensão JPEG.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/sn4p_c4t/imagem4.png)

Abrir os arquivos JPEG, e em um deles estará a flag.
![Packets data flow](https://github.com/brunoavelino/writeup-imectf0x7e1/blob/master/sn4p_c4t/imagem5.png)


