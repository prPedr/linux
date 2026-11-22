# Navegação de Diretórios (`cd`, `pwd`)

Comandos utilizados para se localizar e navegar entre as pastas do sistema de arquivos do Linux.

## Comandos

### `pwd`
Exibe o caminho absoluto completo do diretório atual onde você se encontra (*Print Working Directory*).
```bash
pwd
```

### `cd ..`
Volta um nível na hierarquia de diretórios (vai para o diretório pai).
```bash
cd ..
```

### `cd /`
Vai diretamente para o diretório **raiz** (`/`) do sistema, que é o ponto de partida de toda a estrutura de arquivos do Linux.
```bash
cd /
```

### `cd /sys/kernel`
Acessa um diretório específico utilizando um **caminho absoluto** (que começa a partir da raiz `/`). Neste exemplo, entra na pasta `kernel` que está dentro de `sys`.
```bash
cd /sys/kernel
```