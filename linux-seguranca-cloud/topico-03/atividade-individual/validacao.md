# Validação

## URL testado
`http://192.168.1.110/wordpress/wp-admin/setup-config.php`

## Forma de validação
Navegador Web (Google Chrome) externo acedendo ao IP privado da Máquina Virtual de Laboratório.

## Resultado do teste
O servidor Apache interceptou com sucesso a requisição HTTP e encaminhou-a para o módulo PHP, o qual renderizou perfeitamente a página de boas-vindas do assistente do WordPress. Isto comprova que a comunicação entre o Apache e o motor PHP está totalmente operacional.

## Evidência
O print do assistente gráfico de configuração foi capturado e armazenado na diretoria local de evidências com o nome `instalacao_wordpress.png`.

## Relação entre WordPress, servidor web, PHP e base de dados
1. O **Apache** escuta no porto 80 e recebe o pedido do cliente.
2. O Apache deteta extensões `.php` e passa a execução ao módulo do **PHP**.
3. O PHP processa o código da aplicação do **WordPress** (lógica de negócio).
4. O WordPress realiza chamadas relacionais à base de dados **MariaDB** para gerir posts, utilizadores e configurações estruturadas.

## Cuidados de segurança a considerar no próximo tópico
1. Remoção ou proteção do ficheiro `wp-config-sample.php`.
2. Ocultação das assinaturas de versão do Apache (`ServerTokens Prod`) para dificultar varrimentos (*reconnaissance*).
3. Restrição de listagem de diretórios no Apache (`Options -Indexes`).
