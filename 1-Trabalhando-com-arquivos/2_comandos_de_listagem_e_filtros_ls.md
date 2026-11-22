# Listagem e Filtros (`ls`)

O comando `ls` (*List*) exibe o conteúdo (arquivos e subdiretórios) de uma pasta. Ele pode ser combinado com caminhos, caracteres curinga (*wildcards*) e paginadores.

## Listagem Básica

### `ls`
Lista os arquivos e pastas visíveis no diretório atual em que você se encontra.
```bash
ls
```

### `ls /sys/kernel`
Lista o conteúdo do diretório `/sys/kernel` sem a necessidade de entrar nele antes.
```bash
ls /sys/kernel
```

---

## Paginação com Pipe (`|`)

### `ls | more`
Lista o conteúdo do diretório atual enviando o resultado através de um **pipe** (`|`) para o comando `more`. Isso faz com que a saída seja exibida página por página (útil quando há muitos arquivos).
* **Dica:** Pressione `Espaço` para avançar uma página, `Enter` para avançar uma linha e `q` para sair.
```bash
ls | more
```

### `ls /sys/kernel/ | more`
Faz o mesmo que o comando anterior, mas listando especificamente o conteúdo do diretório `/sys/kernel/` de forma paginada.
```bash
ls /sys/kernel/ | more
```

---

## Uso de Curingas (*Wildcards* / *Globbing*)

### `ls /sys/kernel/p*`
Lista apenas os arquivos e pastas dentro de `/sys/kernel/` cujo nome comece com a letra **`p`**. O asterisco (`*`) representa qualquer sequência de caracteres (ou nenhum).
```bash
ls /sys/kernel/p*
```

### `ls arquivo[1-3].txt`
Lista arquivos que correspondam ao padrão usando um **intervalo numérico**. Neste caso, buscará por: `arquivo1.txt`, `arquivo2.txt` e `arquivo3.txt` (se existirem no diretório).
```bash
ls arquivo[1-3].txt
```

### `ls arquivo[1,3,5].txt`
Lista arquivos que correspondam a **valores específicos** listados dentro dos colchetes. Neste caso, buscará apenas por `arquivo1.txt`, `arquivo3.txt` e `arquivo5.txt` (ignorando o 2 e o 4).
> **Nota:** Em *globbing* padrão do Bash, os colchetes leem caracteres individuais (então `[1,3,5]` também tentaria buscar `arquivo,.txt`). Para listas exatas de palavras ou números sem a vírgula ser interpretada como caractere, o ideal no Bash moderno é usar chaves: `ls arquivo{1,3,5}.txt`.
```bash
ls arquivo[1,3,5].txt
```