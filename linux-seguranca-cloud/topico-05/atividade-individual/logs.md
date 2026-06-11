# 📑 Análise de Registos e Eventos do Sistema (Logs)

Auditoria focada na identificação de anomalias operacionais e tentativas de acesso.

### 1. Logs Recentes do Sistema
* **Comando utilizado:** `sudo tail -n 50 /var/log/syslog` ou `sudo journalctl -n 50`
* **Objetivo:** Inspecionar os últimos eventos gerais registados pelo kernel e serviços de segundo plano.

### 2. Logs do Servidor Web Apache
* **Comando utilizado (Erros):** `sudo tail -n 20 /var/log/apache2/error.log`
* **Comando utilizado (Acessos):** `sudo tail -n 20 /var/log/apache2/access.log`

### 3. Evento Relevante Identificado
* **Ficheiro de Origem:** `/var/log/apache2/access.log`
* **Evento:** Registos de requisições HTTP `GET / HTTP/1.1` com código de resposta `200` (Sucesso) originados pelo IP do anfitrião Windows, confirmando navegação legítima no WordPress, ou registos de erros `404` para recursos inexistentes.
