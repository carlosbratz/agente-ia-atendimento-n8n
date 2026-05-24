# 🧠 Agente de IA Multimodal para Atendimento (WhatsApp)

> **Status do Projeto:** Concluído ✔️

## 🎯 O Problema
Atendimentos automatizados tradicionais (bots de botões) geram frustração pela rigidez e incapacidade de entender contexto. Além disso, clientes enviam áudios, imagens e múltiplos textos curtos seguidos, o que costuma quebrar lógicas simples de automação, resultando em perda de leads qualificados.

## 💡 A Solução (Arquitetura)
Desenvolvimento de um **Master Agent** utilizando **n8n e LangChain**, capaz de atuar como um consultor humano. O sistema compreende contexto, possui memória de longo prazo e processa múltiplas mídias.

### ⚙️ Destaques da Arquitetura:
* **Buffer Inteligente (Redis):** O sistema não responde a cada mensagem isolada. Ele aguarda (buffer) para agrupar mensagens picotadas do usuário, áudios e imagens antes de enviar o bloco completo de contexto para o LLM.
* **Memória de Conversa (PostgreSQL / Supabase):** O agente lembra do histórico do cliente, permitindo conversas fluidas ao longo de dias.
* **Processamento Multimodal (OpenAI):** * Converte áudios para texto (`Whisper`).
  * Analisa imagens enviadas pelo cliente (`GPT-4o-mini Vision`).
  * Extrai dados de documentos PDF.
* **Integração CRM:** Cadastro e consulta automática de leads no banco de dados.

![Arquitetura do Agente IA](workflow-agente.png)

## 🚀 Impacto
* **Experiência Humanizada:** O cliente conversa naturalmente, enviando áudios ou fotos, e a IA responde em formato humanizado e fracionado, respeitando os limites de caracteres do WhatsApp.
* **Redução de Gargalos:** Qualificação automática de leads complexos 24/7.
* **Gestão de Crise:** Ferramenta (Tool) embutida no agente para transferir o atendimento para um humano caso o sentimento da conversa exija.

## 🛠️ Tecnologias Utilizadas
* **n8n** (Orquestração)
* **LangChain & OpenAI** (LLMs, Whisper, Vision, Output Parsers)
* **Redis** (Gerenciamento de Fila e Buffer)
* **Supabase / PostgreSQL** (Banco de Dados e Memória)
* **Evolution API** (Gateway do WhatsApp)

## 📁 Como visualizar
Faça o download do arquivo `workflow-agente-ia.json` presente neste repositório e importe-o para a sua instância do n8n para visualizar a lógica completa.
