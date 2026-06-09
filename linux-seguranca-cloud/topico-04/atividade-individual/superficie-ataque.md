# Superfície de Ataque

## 1. Serviço Web Utilizado no Tópico 3
- **Servidor HTTP:** Apache2 (v2.4)
- **Aplicação:** WordPress CMS (correndo sobre PHP 8.x)

## 2. Serviços Ativos e Portas Observadas
Através de ferramentas de diagnóstico local (como `ss -tulpn` ou `netstat`), foram identificados os seguintes serviços à escuta na máquina virtual:
- **Porta 22/TCP:** Serviço `sshd` (OpenSSH Daemon) - Necessário para a nossa administração remota via PowerShell.
- **Porta 80/TCP:** Serviço `apache2` - Necessário para servir o WordPress via HTTP.
- **Porta 3306/TCP (ou 33060):** Serviço `mariadb` / `mysqld` - Motor de base de dados (deve escutar apenas em `127.0.0.1`).

## 3. Portas Estritamente Necessárias
Para o funcionamento do laboratório atual, apenas são necessárias as portas:
- **22 (SSH)**: Para gestão e configuração da VM.
- **80 (HTTP)**: Para disponibilizar o WordPress e as páginas estáticas ao utilizador externo.

## 4. Identificação de Riscos Iniciais (Mínimo 3)
1. **Exposição desnecessária da Base de Dados:** Se o MariaDB estiver a escutar em todas as interfaces (`0.0.0.0`), a porta 3306 fica exposta a ataques de força bruta vindos da rede externa.
2. **Exibição de Metadados e Versões (Banner Grabbing):** O Apache, por omissão, envia a sua versão exata e o sistema operativo nos cabeçalhos HTTP, facilitando a identificação de exploits específicos por atacantes.
3. **Listagem de Diretorias Ativa:** Sem restrições, o Apache pode permitir que atacantes naveguem pelas pastas internas do WordPress (como `/wp-content/uploads/`) caso não exista um ficheiro de index.
