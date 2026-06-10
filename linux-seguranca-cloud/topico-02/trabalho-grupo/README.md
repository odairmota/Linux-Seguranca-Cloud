# Sessão 2 | Atividade em Grupo (Entrega Adaptada)
## Gestão de Identidades e Acessos (IAM) e Permissões em Linux

Este diretório contém os artefactos desenvolvidos para a Atividade em Grupo da Sessão 2, focada na modelação de políticas de controlo de acesso, desenho de estruturas de diretórios seguras e blindagem do protocolo SSH.

---

### 1. Elementos e Papéis
* **Formando:** Odair  Santos Mota
* **Contexto:** Tópico 02 - IAM, Permissões e Acesso Remoto Seguro

### 2. Estrutura de Diretórios Desenvolvida
O projeto propõe o isolamento da aplicação web na seguinte árvore perimetral:
* 📁 `/opt/projeto-web/public` - Ficheiros públicos (Código Fonte) -> Permissão `775` (Grupo `webops`)
* 📁 `/opt/projeto-web/config` - Configurações e Segredos -> Permissão `740` (Grupo `admins`)
* 📁 `/opt/projeto-web/logs` - Registos do Sistema -> Permissão `750` (Grupo `auditores`)
* 📁 `/opt/projeto-web/docs` - Manuais e Documentação -> Permissão `755` (Grupo `visitantes`)

### 3. Entregáveis Disponíveis nesta Pasta
* 📄 **[Relatório em PDF](grupo-odair-gestao-acessos-topico-02.pdf):** Documento formal contendo tabelas de permissões octais, matriz de riscos IAM e configuração recomendada para o daemon SSH.
* 📁 **[Evidências](evidencias/):** Capturas de ecrã demonstrando os comandos exemplificativos aplicados no laboratório local.
