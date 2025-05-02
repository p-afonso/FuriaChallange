# Workflow Inteligente - FURIA (n8n)

Automação desenvolvida com n8n para atendimento via WhatsApp utilizando inteligência artificial, vetorização de arquivos e integração com Supabase e Evolution API. Voltado para engajamento de fãs da FURIA Esports.

## Visão Geral

O fluxo é composto por:

- Webhook para entrada de mensagens via WhatsApp
- Identificação de tipo de mensagem (texto, imagem, áudio)
- Geração/consulta de sessionID por telefone
- IA para resposta inteligente com contexto via RAG (Retriever-Augmented Generation)
- Vetorização de arquivos do Google Drive
- Follow-up automático com clientes inativos
- Alerta de novos leads em grupo de operadores

![Fluxo n8n](./docs/fluxo-furia.jpeg)

## Estrutura Geral

### 1. Entrada de Mensagens
- **Webhook EVO** recebe dados do WhatsApp
- **Switch** identifica o tipo da mensagem recebida
- **Filtro** redireciona texto para a IA ou atendente humano

### 2. Sessão & Contexto
- Verificação do telefone no Supabase
- Geração de sessionID se necessário
- Armazenamento e recuperação de contexto via Supabase + Postgres Chat Memory

### 3. Agente IA (Furiko)
- Prompt com personalidade definida
- Passos de atendimento definidos no system message
- Respostas baseadas em contexto e dados vetoriais

### 4. Vetorização de Arquivos
- Trigger em pasta específica no Google Drive
- Extração de texto de documentos (PDF, Excel, Google Docs)
- Geração de embeddings com OpenAI
- Armazenamento no vector store do Supabase

### 5. Follow-up Automatizado
- Verificação de chats parados
- Classificação com IA do tipo de encerramento
- Envio de mensagens de retomada ou encerramento

### 6. Aviso de Novo Lead
- Criação de alerta para grupo de WhatsApp com dados do novo contato

## Tecnologias e Serviços

- [n8n](https://n8n.io/)
- [OpenAI GPT-4o e Embeddings](https://platform.openai.com/)
- [Supabase (DB + Vetorstore)](https://supabase.com/)
- [Evolution API (WhatsApp)](https://evolutionapi.com/)
- Google Drive API

## Execução Local

1. Clone este repositório
2. Importe o arquivo JSON no seu ambiente n8n
3. Configure as credenciais nas integrações:
   - OpenAI
   - Supabase
   - Evolution API
   - Google Drive
4. Execute os fluxos e verifique os logs

## Observações

- O agente "Furiko" tem personalidade empolgada e foco total em conteúdos da FURIA.
- Os dados vetoriais são essenciais para respostas precisas via RAG.
- O fluxo está preparado para escalar com múltiplos operadores e múltiplos canais.

---

