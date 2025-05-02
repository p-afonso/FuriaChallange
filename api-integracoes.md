# Integrações

## Supabase
- Armazena mensagens, usuários e embeddings
- Usa RLS para controle de sessão e segurança

## OpenAI
- GPT-4o para geração de resposta
- Embeddings (text-embedding-3-small)

## Evolution API
- Webhook: recebe mensagens
- Envia templates
- Verifica status do contato

## Google Drive
- Detecta novo arquivo
- Baixa, converte (se necessário) e extrai conteúdo
- Envia para vetor store (Supabase)
