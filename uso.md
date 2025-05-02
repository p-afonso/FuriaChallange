# Uso do Sistema

1. **Recebimento de mensagem via WhatsApp**
   - A mensagem chega pelo Evolution e é processada pelo webhook

2. **Classificação**
   - Se for texto, segue para análise
   - Caso contrário, é pausado para atendimento humano

3. **Resposta com IA**
   - A IA responde com base no histórico + dados vetoriais

4. **Adição de documentos**
   - Arquivos adicionados no Google Drive são automaticamente vetorizados e incluídos no contexto das respostas

5. **Follow-up**
   - Se a conversa ficar parada, é enviado um lembrete automático após X horas
