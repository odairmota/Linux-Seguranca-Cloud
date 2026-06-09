### 3. Plano de Hardening Inicial (`hardening.md`)
Este cobre o Nível 3 (Avançado), detalhando as proteções específicas para o Apache e WordPress. Abre o ficheiro (`nano hardening.md`):

```markdown
# Plano de Hardening Inicial

## 1. Serviço Alvo
Stack **LAMP** (Apache2, MariaDB, WordPress) publicado no Tópico 3.

## 2. Riscos Específicos Identificados
- Ataques de força bruta contra o painel administrativo do WordPress (`/wp-admin`).
- Vulnerabilidades conhecidas em componentes ou plugins desatualizados.
- Divulgação de informações sensíveis através de mensagens de erro detalhadas ou ficheiros de exemplo (`wp-config-sample.php`).

## 3. Medidas de Hardening Aplicadas Imediatamente (Neste Tópico)
1. **Isolamento de Portos:** Garantir através do UFW que portas como a do MariaDB (3306) estão totalmente inacessíveis do exterior.
2. **Saneamento do Diretório:** Remoção ou isolamento de ficheiros desnecessários na pasta pública, como scripts de teste ou ficheiros `.txt`/`.php` de exemplo que venham por padrão no pacote do WordPress.
3. **Políticas de Acesso Local:** Configurar o MariaDB para aceitar conexões vindas estritamente do `localhost` (`bind-address = 127.0.0.1`).

## 4. Medidas Estratégicas para os Próximos Tópicos
1. **Configuração de Segurança no Apache:**
   - Adicionar as diretivas `ServerTokens Prod` e `ServerSignature Off` no ficheiro `/etc/apache2/conf-available/security.conf` para ocultar a versão do servidor.
   - Desativar a listagem de ficheiros injetando `Options -Indexes` nas diretorias do site.
2. **Cifragem de Tráfego (HTTPS):** Implementação de certificados digitais TLS/SSL no Apache para proteger os dados de autenticação em trânsito.
3. **Hardening do WordPress:** Alterar o prefixo padrão das tabelas da base de dados (`wp_`) e aplicar permissões restritas de leitura ao ficheiro de credenciais `wp-config.php` (`chmod 600` ou `640`).
