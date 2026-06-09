# Validação de Segurança

## 1. URLs Testados pós-Firewall
- `http://192.168.1.110/wordpress` (Aplicação CMS)
- `http://192.168.1.110/topico-03` (Site Estático)

## 2. Resultado dos Testes
- **Acesso Web:** Ambas as rotas continuam totalmente operacionais e acessíveis a partir do navegador da máquina anfitriã, provando que a regra `ufw allow 80/tcp` funcionou perfeitamente.
- **Acesso SSH:** A sessão SSH ativa na PowerShell não caiu e novas conexões são estabelecidas com sucesso devido à regra `ufw allow 22/tcp`.
- **Bloqueio de Portos Externos:** Tentativas de mapeamento ou varrimento externo a outras portas do sistema são agora rejeitadas silenciosamente pelo UFW.

## 3. Evidências
*(Prints do estado do UFW ativo no terminal e logs de acessos válidos guardados na diretoria `evidencias/`)*
