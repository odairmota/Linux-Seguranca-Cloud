# 📊 Relatório de Monitorização de Recursos do Sistema

Métricas de desempenho coletadas no ambiente de laboratório para avaliar a saúde do servidor Linux.

### 1. Tempo de Atividade (Uptime)
* **Comando utilizado:** `uptime`
* **Análise:** Avalia há quanto tempo o servidor está ligado e as médias de carga do processador (*load average*) nos últimos 1, 5 e 15 minutos.

### 2. Consumo de Memória RAM
* **Comando utilizado:** `free -h`
* **Análise:** Exibe a memória total, utilizada, livre e em cache de forma legível (Ex: MB/GB). Garante que a Stack LAMP não está a esgotar a memória física.

### 3. Espaço em Disco
* **Comando utilizado:** `df -h /`
* **Análise:** Monitoriza a ocupação da partição raiz. Fundamental para evitar que o servidor pare por falta de armazenamento devido ao crescimento das tabelas do MariaDB ou ficheiros de log.

### 4. Estado do Serviço Web (Apache/WordPress)
* **Comando utilizado:** `sudo systemctl status apache2`
* **Análise:** Confirma se o daemon do servidor web está no estado `active (running)`, validando a disponibilidade da aplicação para os utilizadores.
