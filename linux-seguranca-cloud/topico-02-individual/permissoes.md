# Permissões aplicadas

## Ambiente utilizado
VM Local (Ubuntu Server executado em ambiente de virtualização isolado).

## Utilizador e grupos
* **Output do comando `whoami`**: ` osboxes`
* **Output do comando `id`**: ` uid=1000(osboxes) gid=1000(osboxes) groups=1000(osboxes),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users)`
* **Output do comando `groups`**: ` osboxes adm cdrom sudo dip plugdev users`

## Ficheiros criados
* **publico.txt**: Ficheiro de texto padrão destinado a conter informações gerais legíveis por qualquer utilizador do sistema.
* **restrito.txt**: Ficheiro contendo dados sensíveis ou configurações internas que não devem ser expostas publicamente.
* **script.sh**: Script em shell de automação para testes de execução local.

## Permissões aplicadas

| Ficheiro | Permissão | Justificação |
| :--- | :---: | :--- |
| **publico.txt** | `644` (`-rw-r--r--`) | O proprietário tem permissão de leitura e escrita (`rw-`).
 O grupo proprietário e os restantes utilizadores do sistema possuem apenas permissão de leitura (`r--`).
 Garante a integridade do ficheiro contra modificações não autorizadas por terceiros, mantendo a visibilidade. |
| **restrito.txt** | `640` (`-rw-r-----`) | O proprietário mantém acesso total de leitura e escrita (`rw-`).
 Os membros do grupo proprietário podem apenas ler o ficheiro (`r--`), enquanto qualquer outro utilizador externo
 (others) não possui qualquer tipo de acesso (`---`), mitigando o risco de fuga de informação. |
| **script.sh** | `755` / `u+x` | Adiciona explicitamente o privilégio de execução (`x`) ao proprietário do ficheiro.
 Essencial para que o interpretador de comandos (shell) possa invocar o script diretamente como um binário executável `./script.sh`. |

## Relação com o princípio do menor privilégio
O princípio do menor privilégio (*Principle of Least Privilege - PoLP*) dita que a qualquer entidade (utilizador, processo ou sistema) deve ser concedido apenas o nível estritamente necessário de acessos para a execução das suas funções legítimas.

Ao aplicar permissões restritivas como `640` e `644` em vez de permissões totais (`777`), mitigamos riscos críticos de segurança:
1. **Prevenção de Alterações Não Autorizadas:** Impede que utilizadores comuns ou processos maliciosos sem privilégios alterem ficheiros de configuração ou scripts do sistema.
2. **Confidencialidade dos Dados:** Garante que dados sensíveis (no caso do `restrito.txt`) fiquem inacessíveis para utilizadores que partilham o mesmo servidor, mas que não pertencem ao escopo da administração do serviço web.
3. **Controlo de Execução:** Evita que ficheiros de texto comuns sejam interpretados erroneamente como binários ou scripts executáveis, bloqueando potenciais vetores de escalonamento de privilégios e injeção de código arbitrário.
