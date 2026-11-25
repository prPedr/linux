# Acesso Remoto (SSH) e Edição de Arquivos (`vim`)

Comandos voltados para a visualização e edição de arquivos de configuração do sistema — com foco no serviço de acesso remoto **SSH** (*Secure Shell*) no **Ubuntu**.

## Visualização e Edição

### `cat /etc/ssh/sshd_config`
Exibe no terminal o conteúdo do arquivo de configuração principal do servidor SSH (`sshd_config`), permitindo consultar como o serviço está configurado no momento (porta, métodos de autenticação, permissões de login, etc.).
```bash
cat /etc/ssh/sshd_config
```

### `vim /etc/ssh/sshd_config`
Abre o arquivo de configuração do servidor SSH no editor de texto **Vim**. 
> **Nota:** Como `/etc/ssh/sshd_config` pertence ao sistema (`root`), caso você não esteja logado como `root`, será necessário abrir o arquivo com `sudo vim /etc/ssh/sshd_config` para conseguir salvar as alterações.

* **Dicas rápidas de uso no Vim:**
  * Pressione **`i`** para entrar no modo de inserção (*Insert*) e editar o texto.
  * Pressione **`Esc`** para sair do modo de inserção.
  * Digite **`:wq`** e pressione `Enter` para salvar e sair (*write & quit*), ou **`:q!`** para sair sem salvar.

```bash
vim /etc/ssh/sshd_config
```

---

## Configuração do SSH (`PermitRootLogin`)

### Habilitar login remoto como `root` (`PermitRootLogin yes`)
Dentro do arquivo `/etc/ssh/sshd_config`, localize a diretiva `#PermitRootLogin prohibit-password` (ou similar), remova o `#` do início (para descomentar a linha) e altere o valor para `yes`:

```text
PermitRootLogin yes
```

* **O que isso faz:** Permite que o usuário `root` faça login diretamente na máquina via SSH usando senha (o que vem bloqueado por padrão no Ubuntu por segurança).
* **Importante:** Após salvar o arquivo, é necessário reiniciar o serviço SSH para que a alteração entre em vigor (`sudo systemctl restart ssh`).