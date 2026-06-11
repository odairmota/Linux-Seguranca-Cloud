# 🏁 Plano de Continuidade Operacional da Infraestrutura

Estratégia planeada para garantir a alta disponibilidade e resiliência da Stack LAMP.

### 1. Serviços Críticos Mapeados
* **Servidor Web:** Apache (`apache2`)
* **Motor de Base de Dados:** MariaDB (`mariadb`)

### 2. Ficheiros e Configurações Críticas
* Código fonte e uploads do CMS: `/var/www/html/wordpress/`
* Configurações de conexão e chaves: `wp-config.php`
* Diretivas do Servidor Web: `/etc/apache2/sites-available/000-default.conf`

### 3. Logs de Auditoria Obrigatória
* `/var/log/apache2/error.log` (Erros de runtime PHP e quebras de serviço)
* `/var/log/mysql/error.log` (Falhas de integridade em tabelas Indexed)

### 4. Política e Periodicidade de Backups
* **Ficheiros Web:** Backup Incremental diário às 02:00 AM; Backup Completo semanal (Retenção de 30 dias).
* **Base de Dados (Dump SQL):** Backup Lógico completo a cada 6 horas via `mysqldump` automatizado por tarefas `cron`.

### 5. Critérios de Validação Pós-Recuperação
1. **Consistência do Serviço:** Validar o estado ativo dos daemons com `systemctl`.
2. **Integridade de Dados:** Executar `mysqlcheck -u root -p --all-databases` pós-restauro.
3. **Validação Logística:** Testar se o site carrega sem erros 500 no browser externo.
