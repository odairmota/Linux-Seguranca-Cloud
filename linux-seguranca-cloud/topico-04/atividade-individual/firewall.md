# Configuração de Firewall (UFW)

## 1. Verificação do Estado Inicial
O utilitário UFW (Uncomplicated Firewall) foi validado no sistema. Inicialmente encontrava-se desativado (`Status: inactive`).

## 2. Regras de Filtragem Aplicadas
Para mitigar a superfície de ataque sem perder o acesso remoto à máquina virtual, foram aplicadas as seguintes regras estritas:

```bash
# Permitir tráfego de administração SSH (Crucial para não perder a ligação)
sudo ufw allow 22/tcp

# Permitir tráfego web padrão para o Apache e WordPress
sudo ufw allow 80/tcp

# Ativar o Firewall
sudo ufw enable
