# Manipulação de Arquivos e Diretórios (`touch`, `mkdir`, `rmdir`, `rm`)

Comandos voltados para a criação, remoção, alteração e gerenciamento de arquivos e pastas no sistema.

## Arquivos (`touch`, `rm`)

### `touch arquivo1.txt`

Cria um arquivo vazio chamado `arquivo1.txt` no diretório atual.

* **Curiosidade:** Se o arquivo `arquivo1.txt` já existir, o comando `touch` não apaga seu conteúdo; ele apenas atualiza o *timestamp* (data e hora de último acesso/modificação) do arquivo.

```bash
touch arquivo1.txt
```

### `touch texto1.txt texto2.txt`

Cria dois arquivos vazios de uma só vez (`texto1.txt` e `texto2.txt`) no diretório atual. Basta separar os nomes por espaço.

```bash
touch texto1.txt texto2.txt
```

### `rm texto1.txt`

Remove (apaga) o arquivo `texto1.txt` do diretório atual.

> **Atenção:** No terminal Linux, a remoção com `rm` não envia o arquivo para a lixeira — a exclusão é direta.

```bash
rm texto1.txt
```

### `rm texto*`

Apaga todos os arquivos (ou itens correspondentes) no diretório atual cujo nome comece com `texto`, utilizando o curinga `*`.

```bash
rm texto*
```

---

## Diretórios (`mkdir`, `rmdir`, `rm -rf`)

### `mkdir Documentos`

Cria uma nova pasta (diretório) chamada `Documentos` dentro do diretório atual (*Make Directory*).

```bash
mkdir Documentos
```

### `mkdir 'Planejamento 2027'`

Cria uma pasta cujo nome contém espaço (`Planejamento 2027`). As aspas simples garantem que o shell trate o texto como um único nome de diretório em vez de dois argumentos separados.

```bash
mkdir 'Planejamento 2027'
```

### `mkdir Escolares Financeiras`

Cria duas pastas de uma única vez (`Escolares` e `Financeiras`) no diretório atual.

```bash
mkdir Escolares Financeiras
```

### `rmdir Documentos`

Remove o diretório `Documentos` **apenas se ele estiver vazio** (*Remove Directory*).

> **Erro comum (`Directory not empty`):** Se houver arquivos ou subpastas dentro de `Documentos`, o comando falhará e exibirá algo como:
> `rmdir: failed to remove 'Documentos/': Directory not empty`

```bash
rmdir Documentos
```

### `rmdir Escolares Financeiras`

Apaga as duas pastas (`Escolares` e `Financeiras`) de uma vez, desde que ambas estejam vazias.

```bash
rmdir Escolares Financeiras
```

### `rm -rf Documentos`

Remove o diretório `Documentos` de forma **recursiva** (`-r`, apagando tudo que estiver dentro dele, incluindo arquivos e subpastas) e **forçada** (`-f`, sem pedir confirmação).

> **Cuidado redobrado:** Esse é um comando destrutivo e irreversível no terminal. Confira bem o caminho/nome do diretório antes de executar para não apagar nada importante por engano.

```bash
rm -rf Documentos
```

### `rm -rfv teste`

Remove o diretório `teste` recursivamente (`-r`) e de forma forçada (`-f`), mas adiciona o modo **verboso** (`-v` / *verbose*), exibindo no terminal cada arquivo e subdiretório que está sendo apagado em tempo real.

```bash
rm -rfv teste
```

### `rm -rfvi teste`

Combina as opções anteriores com o modo **interativo** (`-i` / *interactive*). Mesmo com `-f`, o `-i` (por vir depois na ordem das *flags*) faz com que o sistema peça confirmação (`y` para sim, `n` para não) antes de remover cada item, enquanto exibe o progresso (`-v`).

```bash
rm -rfvi teste
```