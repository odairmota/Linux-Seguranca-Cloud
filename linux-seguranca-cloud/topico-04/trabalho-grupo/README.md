# Sessão 4 | Atividade em Grupo (Entrega Adaptada)
## Plano de Segurança Inicial e Hardening Perimetral

Este diretório contém o desenvolvimento da Atividade em Grupo da Sessão 4, adaptada para execução e entrega individual por motivos de força maior. O foco do projeto assenta na modelação de uma estratégia de segurança inicial para mitigar riscos e reduzir a superfície de ataque de um servidor web em produção.

---

### 1. Identificação do Trabalho
* **Formando:** Odair Santos Mota
* **Perfil Profissional:** Administrador de Sistemas Linux
* **Contexto:** Tópico 04 - Segurança e Hardening de Infraestruturas Cloud

### 2. Cenário Técnico Analisado
* **Cenário Selecionado:** Cenário C – Sistema de Gestão de Conteúdos (CMS) **WordPress** publicado sobre Servidor Web **Apache** e Base de Dados **MariaDB** (Stack LAMP desenvolvido no Tópico 03).
* **Objetivo Principio:** Aplicação de regras de filtragem perimetral via Firewall (`ufw`) e isolamento de serviços críticos na interface local (`127.0.0.1`).

---

### 3. Estrutura de Entrega e Artefactos

A pasta foi organizada rigorosamente de acordo com os requisitos obrigatórios do enunciado:

* 📄 **[Relatório Oficial em PDF](grupo-odair-seguranca-hardening-topico-04.pdf):** Documento formal contendo a caraterização do serviço, mapeamento exaustivo da superfície de ataque, regras de firewall propostas, matriz de hardening inicial e plano de validação.
* 📁 **[Pasta de Evidências](evidencias/):** Diretório central que armazena os registos visuais (prints) que comprovam o sucesso da implementação dos testes de segurança.

---

### 4. Resumo de Implementação Perimetral (Firewall UFW)

Abaixo encontra-se a tabela de diretivas aplicadas e validadas no ambiente de laboratório Linux Ubuntu:

| Serviço Alvo | Porto / Protocolo | Decisão Aplicada | Justificação Operacional |
| :--- | :---: | :---: | :--- |
| **SSH** | 22 / TCP | **PERMITIR** | Canal seguro de administração remota do Engenheiro Informático à VM. |
| **HTTP** | 80 / TCP | **PERMITIR** | Entrada de tráfego legítimo para navegação no ecossistema WordPress. |
| **HTTPS** | 443 / TCP | **BLOQUEAR** | Porta fechada temporariamente até à futura instalação de certificados SSL/TLS. |
| **MariaDB** | 3306 / TCP | **BLOQUEAR** | Isolamento total do motor de banco de dados do exterior. Comunicação puramente local. |

---

### 5. Repositório de Evidências Fotográficas

Os resultados operacionais descritos no plano de validação podem ser auditados diretamente através das capturas armazenadas na subpasta de evidências deste diretório:

1. **Estado Ativo da Firewall:** Comprovação do estado `active` do UFW e regras em lote.
2. **Conetividade Web:** Validação de acesso ao instalador do WordPress a partir do navegador do anfitrião Windows.
3. **Persistência do Canal SSH:** Verificação de integridade da sessão remota na PowerShell pós-ativação do firewall.
4. **Isolamento de Base de Dados:** Demonstração do encerramento de escuta externa do porto 3306.

---
*Para uma análise aprofundada das métricas de risco e ações de hardening executadas na diretoria pública do Apache, consulte o relatório técnico em anexo no topo desta página.*
