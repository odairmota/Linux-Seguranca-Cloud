# Acesso remoto e chaves SSH

## Diferença entre autenticação por palavra-passe e autenticação por chave

* **Autenticação por Palavra-passe:** Baseia-se num segredo partilhado tradicional. O utilizador envia a password para o servidor, que a valida. É vulnerável a ataques de força bruta (*brute-force*), interceptação de tráfego (*man-in-the-middle*) e engenharia social.
* **Autenticação por Chave SSH:** Utiliza criptografia assimétrica (um par de chaves pública/privada). O servidor envia um desafio cifrado que só pode ser assinado pela chave privada correspondente no cliente. A password nunca viaja pela rede, tornando o processo imune a ataques de dicionário ou força bruta automatizada.

## Chave pública
A chave pública é guardada no ficheiro `~/.ssh/id_ed25519_teste.pub`. Ela funciona como o identificador que é instalado nos servidores remotos (dentro do ficheiro `~/.ssh/authorized_keys`). Como o nome indica, pode ser partilhada publicamente sem colocar o sistema em risco.

## Chave privada
A chave privada é guardada no ficheiro `~/.ssh/id_ed25519_teste`. É o componente crítico de segurança que deve permanecer exclusivamente na máquina do administrador (`osboxes`). O acesso a este ficheiro permite o controlo total dos servidores associados.

## Cuidados de segurança
Para manter um ambiente de acesso remoto robusto, devem ser seguidas as seguintes boas práticas:
1. **Uso de Passphrase:** Cifrar a chave privada local com uma frase de segurança (*passphrase*) forte para mitigar riscos caso o equipamento físico seja roubado.
2. **Permissões Restritivas:** O diretório `~/.ssh` deve ter permissão estrita `700` (`drwx------`) e a chave privada deve ter `600` (`-rw-------`). O serviço OpenSSH rejeita a ligação se detetar permissões inseguras.
3. **Desativar Autenticação por Password:** No servidor, alterar a configuração em `/etc/ssh/sshd_config` definindo `PasswordAuthentication no`, forçando o uso exclusivo de chaves.

## Evidência segura
Abaixo está a listagem do diretório `.ssh` obtida através do comando `ls -l ~/.ssh`, demonstrando a criação correta das chaves com as permissões nativas de segurança do Linux:
total 8
-rw------- 1 osboxes osboxes   0 Jun 10  2025 authorized_keys
-rw------- 1 osboxes osboxes 411 Jun  4 19:29 id_ed25519_teste
-rw-r--r-- 1 osboxes osboxes  98 Jun  4 19:29 id_ed25519_teste.pub
