# Publicação do Serviço Web

## Nível escolhido
Nível 3 - Avançado

## Rota escolhida
Apache (Stack LAMP)

## Componentes usados
- **Servidor web:** Apache2
- **PHP:** Interpretador ativo com extensões (php-mysql, php-xml, php-gd, php-mbstring, php-imagick, php-zip, php-intl)
- **Base de dados:** MariaDB Server
- **WordPress:** Versão mais recente descarregada em Português

## Pasta de publicação
`/var/www/html/wordpress`

## URL de acesso
`http://192.168.1.110/wordpress`

## Estado da instalação
Instalador aberto com sucesso no navegador. O ambiente está pronto para a criação do ficheiro `wp-config.php` através da interface gráfica.

## Comandos principais utilizados
```bash
# Instalação dos pacotes base
sudo apt update && sudo apt upgrade -y
sudo apt install apache2 mariadb-server php libapache2-mod-php php-mysql php-xml php-gd php-mbstring php-imagick php-zip php-intl -y

# Ativação dos serviços no systemd
sudo systemctl start apache2 && sudo systemctl enable apache2
sudo systemctl start mariadb && sudo systemctl enable mariadb

# Download e extração da aplicação
cd /tmp
wget [https://pt.wordpress.org/latest-pt_PT.tar.gz](https://pt.wordpress.org/latest-pt_PT.tar.gz)
tar -xvf latest-pt_PT.tar.gz
sudo mv wordpress /var/www/html/

# Ajuste crítico de permissões para o Apache
sudo chown -R www-data:www-data /var/www/html/wordpress
sudo chmod -R 755 /var/www/html/wordpress
