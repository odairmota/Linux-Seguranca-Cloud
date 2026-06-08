# Atividade prática individual - Tópico 3

## Nível realizado
Nível 3 - Avançado (com validação complementar do Nível 2)

## Objetivo
Criar, publicar, validar e documentar um pequeno serviço na web em ambiente Linux. A atividade contemplou a publicação de páginas estáticas e a implementação estruturada de uma aplicação CMS WordPress utilizando a Stack LAMP.

## Ambiente utilizado
VM Local (Ubuntu Server disponibilizado em ambiente de laboratório), acedida e administrada remotamente via SSH através da PowerShell do Windows.

## Rota de publicação
WordPress com Apache (Servidor HTTP Apache2, interpretador PHP e motor de base de dados MariaDB).

## Ficheiros criados
- `site/index.html` (Página inicial estática)
- `site/sobre.html` (Página de descrição complementar)
- `site/style.css` (Folha de estilos para customização visual)
- `wordpress/wp-config-sample.php` (Ficheiro de parametrização do CMS)
- `comandos.txt` (Histórico de comandos executados no terminal)
- `publicacao.md` (Relatório técnico de provisionamento do serviço)
- `validacao.md` (Documentação dos testes de conectividade e arquitetura)
- `README.md` (Documento de síntese global)

## URLs testados
- **Aplicação WordPress (Nível 3):** `http://192.168.1.110/wordpress`
- **Página Web Estática (Nível 2):** `http://192.168.1.110/topico-03`

## Evidências produzidas
- Print do assistente gráfico de configuração inicial do WordPress capturado via browser e armazenado em `evidencias/instalacao_wordpress.png`.
- Validação local de resposta HTTP 200 OK através do utilitário `curl` no terminal Linux.
- Logs de acesso estruturados em `/var/log/apache2/access.log`.

## Dificuldades encontradas
O principal desafio consistiu no correto mapeamento de privilégios e permissões de escrita na diretoria de publicação do Apache. Foi necessário alterar a propriedade recursiva da pasta para o utilizador e grupo do servidor web (`chown -R www-data:www-data`), garantindo que o interpretador PHP conseguisse criar e modificar os ficheiros de configuração dinamicamente sem bloqueios do sistema de ficheiros do Linux.

## Link do repositório GitHub
[Meu Repositório - Linux Segurança Cloud](https://github.com/odairmota/Linux-Seguranca-Cloud)

## Próximos passos
Para o Tópico 4, o foco será direcionado para o hardening e auditoria de segurança da stack web implementada:
1. Desativar a listagem pública de diretórios no Apache aplicando a diretiva `Options -Indexes`.
2. Ocultar assinaturas e metadados de versão do Apache (`ServerTokens Prod` e `ServerSignature Off`) e do PHP para mitigar ações de reconhecimento (*reconnaissance*).
3. Configurar regras estritas de filtragem de tráfego através do Firewall (UFW), limitando os portos expostos apenas ao estritamente necessário (HTTP/HTTPS e SSH administrado).
