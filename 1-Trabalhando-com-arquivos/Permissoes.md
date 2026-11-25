# 👥 Usuários, Grupos e Privilégios (`passwd`, `su`)

Comandos voltados para a visualização de grupos do sistema, gerenciamento de senhas e troca de sessão de usuário no terminal (testados em distribuição **Ubuntu**).

## Comandos

### `cat /etc/group`
O comando `cat` (*Concatenate*) lê e exibe todo o conteúdo de um arquivo diretamente no terminal. Ao apontar para `/etc/group`, ele lista todos os **grupos de usuários** cadastrados no sistema, mostrando o nome do grupo, o ID numérico (GID) e os usuários que pertencem a cada um.
```bash
cat /etc/group
```

### `sudo passwd root`
Permite definir ou alterar a senha do superusuário (`root`), executando o comando `passwd` com privilégios elevados (`sudo`).
* **Contexto no Ubuntu:** Por padrão, distribuições baseadas em Ubuntu vêm com a conta `root` desabilitada/bloqueada por questões de segurança, incentivando o uso do `sudo` no dia a dia. Ao rodar `sudo passwd root` e cadastrar uma senha, você ativa o login direto como `root`.
```bash
sudo passwd root
```

### `su testeserver`
O comando `su` (*Switch User*) permite trocar o usuário ativo na sessão atual do terminal — neste exemplo, alternando para o usuário `testeserver`.
* **Dica:** Se você estiver logado como `root`, a troca para um usuário comum como `testeserver` ocorre sem pedir senha. Caso contrário, será solicitada a senha do usuário de destino. Para voltar ao usuário anterior, basta digitar `exit`.
```bash
su testeserver
```