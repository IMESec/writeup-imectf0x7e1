# NOPATTERN
## Enunciado
Você encontrou um arquivo .zip que contém uma chave para decriptografar uma cifra. Encontre esta chave.

## Solução
Ao utiilzarmos a ferramenta _strings_, juntamente com _grep_, para tentar encontrar a chave utilizando a busca pela palavra _Key_,
```bash
strings recovery.zip | grep Key
```
obteremos a seguinte saída:
```bash
Key: PLAINTEXTISEASYTOC
```
Portanto, a flag é PLAINTEXTISEASYTOC
