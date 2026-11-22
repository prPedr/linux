# Manipulação de Arquivos e Diretórios (`touch`, `mkdir`)

Comandos voltados para a criação, alteração e gerenciamento de arquivos e pastas no sistema.

## Arquivos (`touch`)

### `touch arquivo1.txt`
Cria um arquivo vazio chamado `arquivo1.txt` no diretório atual.
* **Curiosidade:** Se o arquivo `arquivo1.txt` já existir, o comando `touch` não apaga seu conteúdo; ele apenas atualiza o *timestamp* (data e hora de último acesso/modificação) do arquivo.
```bash
touch arquivo1.txt
```

---

## Diretórios (`mkdir`)

### `mkdir Documentos`
Cria uma nova pasta (diretório) chamada `Documentos` dentro do diretório atual (*Make Directory*).
```bash
mkdir Documentos
```