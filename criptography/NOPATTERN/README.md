# NOPATTERN
## Enunciado
Há um arquivo, codes. Identifique a mensagem profunda que ele carrega.

## Solução
  Não havendo extensão explícita no arquivo _codes_, rodamos a ferramenta _file_:
```bash
$ file codes
```
  A saída é
```bash
codes: bzip2 compressed data, block size = 900k
```
  Ou seja, _codes_ é um arquivo do tipo bzip. Descompatemo-lo:
```bash
$ bunzip2 codes
```
  Um arquivo _codes.out_ é extraído. Apesar de sua extensão ser _out_, se executarmos _file_ novamente, obteremos a seguinte saída:
```bash
codes.out: ASCII text
```
  Rodando a ferramenta _cat_, verificaremos a seguinte saída:
```bash
77, 0o125, 0o60, 0o172, 0b1010101, 0b1111010, 0o116, 0b1000100, 101, 0o60, 0o167, 0x78, 0x52, 0x6a, 0b1001110, 0b1100110, 0o115, 84, 0b1010110, 0x66, 0o125, 0x6a, 0o122, 0o117, 82, 0b1000100, 0b1000010, 79, 102, 0b1010001, 0x6f, 0x3d
```
  Notamos que são vários números em várias representações. Notamos também que nenhum desses números ultrapassa 255. Induz-se que eles são correspondentes a códigos ASCII de caracteres. Criaremos um _script_ em _Python_ para transformar cada um desses números (que estão em diferentes representações) em caracteres:
```python
#!/usr/bin/python

hexa_array = [77, 0o125, 0o60, 0o172, 0b1010101, 0b1111010, 0o116, 0b1000100, 101, 0o60, 0o167, 0x78, 0x52, 0x6a, 0b1001110, 0b1100110, 0o115, 84, 0b1010110, 0x66, 0o125, 0x6a, 0o122, 0o117, 82, 0b1000100, 0b1000010, 79, 102, 0b1010001, 0x6f, 0x3d]

char_string = ""
for i in hexa_array:
    char_string = char_string + chr(i)

print char_string
```
