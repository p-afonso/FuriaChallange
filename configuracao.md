# Configuração

1. **Importar workflow**
   - Use o arquivo `Furia_Workflow.json` no painel do n8n

2. **Credenciais necessárias:**
   - OpenAI (GPT-4o e embeddings)
   - Supabase (chave e URL)
   - Evolution API (chave e ID do bot)
   - Google Drive (OAuth)

3. **Variáveis de ambiente:**
   - `OPENAI_API_KEY`
   - `SUPABASE_URL`
   - `SUPABASE_SERVICE_ROLE`
   - `VECTOR_STORE_TABLE`
   - `EVOLUTION_API_KEY`
   - `WHATSAPP_BOT_ID`

4. **Ative o webhook:**
   - Configure o Evolution para apontar para o webhook público gerado pelo n8n
