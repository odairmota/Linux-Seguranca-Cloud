# Trabalho de Grupo - Sessão 3 | Criação e Publicação de Serviço Web
## Unidade: Linux, Segurança e Cloud

---

## 👤 Identificação do Autor
* **Formando:** Odair Ressurreição Santos Mota
* **Função:** Engenheiro de Sistemas e Administrador de Infraestrutura Web

---

## 🚀 Descrição do Projeto
Este repositório contém a proposta técnica para o desenho, publicação e validação de um serviço web dinâmico sobre um ambiente Linux seguro. O cenário foi estruturado simulando uma infraestrutura real de produção, aplicando controlos rígidos de acesso, isolamento de processos e mitigação de vulnerabilidades.

### 🛠️ Especificações da Rota Escolhida
* **Serviço Publicado:** Aplicação Web com CMS (**WordPress**)
* **Servidor Web:** Apache HTTP Server
* **Pilha Tecnológica (LAMP):** Linux (Ubuntu Server), Apache, MariaDB/MySQL e PHP
* **Porta de Escuta:** 80 (HTTP)
* **Diretório de Publicação:** `/var/www/html/`

---

## 📂 Estrutura de Ficheiros do Tópico 03
A organização desta diretoria no repositório segue os requisitos da atividade. Nota que, devido à equivalência prática e técnica entre os cenários, as capturas de ecrã e validações encontram-se centralizadas na diretoria da atividade individual:

```text
topico-03/
├── atividade-individual/
│   └── evidencias/                                     # Repositório central de prints e validações
└── trabalho-grupo/
    ├── README.md                                       # Este ficheiro de documentação
    └── grupo-odair-publicacao-servico-web-topico-03.pdf  # Relatório técnico finalizado
📋 Resumo das Tarefas Executadas
Instalação e Hardening do Apache: Configuração do servidor web e parametrização do arranque automático com o sistema.

Provisionamento de Base de Dados: Criação de base de dados isolada no MariaDB com utilizador e permissões restritas.

Segregação de Permissões: Distribuição de propriedade dos ficheiros para o utilizador de sistema www-data e isolamento de ficheiros de configuração confidenciais.

Plano de Validação: Testes de conectividade locais (via terminal com curl) e remotos (através do navegador na máquina hospedeira).

📄 Relatório Técnico e Evidências
O planeamento detalhado, a matriz de riscos e as respetivas medidas de mitigação encontram-se descritos no relatório oficial em formato PDF.

📥 Aceda ao relatório aqui: grupo-odair-publicacao-servico-web-topico-03.pdf

📸 Aceda às evidências técnicas aqui: Pasta de Evidências (Atividade Individual)
