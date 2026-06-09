# Atividade prática individual - Tópico 4

## Nível realizado
Nível 3 - Avançado (Plano de hardening completo com implementação prática de regras de firewall do Nível 2).

## Objetivo
Analisar a superfície de ataque da stack LAMP montada no Tópico 3, aplicar políticas estritas de filtragem de tráfego com UFW e traçar um plano de hardening estruturado para mitigar riscos operacionais.

## Ambiente utilizado
VM Local (Ubuntu Server), administrada remotamente via SSH através da PowerShell do Windows.

## Rota de publicação
Apache, MariaDB e WordPress protegidos por Firewall Ativo.

## Ficheiros criados
- `superficie-ataque.md`
- `firewall.md`
- `hardening.md`
- `validacao.md`
- `comandos.txt`
- `README.md`

## URLs testados
- `http://192.168.1.110/wordpress`
- `http://192.168.1.110/topico-03`

## Evidências produzidas
- Prints do terminal com o estado detalhado do UFW ativo e regras aplicadas, armazenados na diretoria `evidencias/`.

## Dificuldades encontradas
Garantir o isolamento preventivo dos portos de base de dados e garantir a ordem correta de ativação do UFW para evitar um bloqueio acidental da própria sessão administrativa SSH ativa.

## Link do repositório GitHub
[Meu Repositório - Linux Segurança Cloud](https://github.com/odairmota/Linux-Seguranca-Cloud)
