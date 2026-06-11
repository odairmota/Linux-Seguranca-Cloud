# 💾 Plano Prático de Backup e Recuperação Simples

Demonstração do procedimento de salvaguarda e validação de integridade dos dados da aplicação.

### 1. Diretório Crítico Identificado
O diretório de produção da aplicação web: `/opt/projeto-web/` (ou a pasta pública do Apache `/var/www/html/wordpress/`).

### 2. Criação do Backup (Compactação Criptográfica/Nativa)
Comando utilizado para gerar o arquivo compactado com preservação de permissões (`-p`):
```bash
sudo tar -cvpzf /backup-projeto-web.tar.gz /opt/projeto-web/
