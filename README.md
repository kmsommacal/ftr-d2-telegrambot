***

# Bot de Clima no Telegram com N8N 🌤

### Descrição do Projeto
Este projeto consiste em um chatbot desenvolvido na plataforma **N8N** que permite aos usuários consultar a temperatura atual de qualquer cidade brasileira diretamente pelo **Telegram**. O bot recebe o nome da cidade, processa a informação e utiliza a API do **OpenWeather** para retornar uma mensagem amigável com o clima em tempo real.

---

### 🚀 Iniciando o n8n
Pata iniciar o n8n localmente utilize docker (Docker Desktop, docker, docker-compose)
1. Crie um arquivo .env com as variáveis indicadas no template (.env-template)
2. Siga as instruções abaixo para criar os tokens/keys caso ainda não tenha criado.
3. Execute o o docker-compose ( docker-compose up -d )
4. Crie sua conta no n8n ou acesse com uma conta já existente.

---

### 🚀 Como Importar o Workflow
Para utilizar este chatbot no seu ambiente N8N, siga os passos abaixo:
1. Faça o download do arquivo `workflow-chatbot-telegram.json` presente neste repositório.
2. No seu N8N, abra a interface de workflows e utilize a opção de **importar arquivo JSON**.
3. Certifique-se de que todos os nós foram carregados corretamente.

---

### 🔑 Configuração de Credenciais
Para que o bot funcione, você precisará configurar duas variáveis de ambiente/credenciais principais no N8N:

1.  **TELEGRAM_BOT_TOKEN**:
    *   Obtenha seu token criando um novo bot através do [@BotFather](https://t.me/botfather) no Telegram.
    *   Insira esse token na credencial do nó **Telegram Trigger**.
2.  **OPENWEATHER_API_KEY**:
    *   Crie uma conta gratuita no site [OpenWeather](https://home.openweathermap.org/users/sign_up).
    *   Gere sua chave de API e insira-a no nó de **HTTP Request** que consulta o clima.
3. É necessário criar as credenciais de acesso para o Telegram e o Openweather nos nós Telegram Trigger e HTTP Request. Utilizando a versão community não é simples de adicionar variáveis globais/projeto.
4. Também é necessário alterar o valor do parâmetro appid no nó HTTP Request para incluir a API key do Openweather.
---

### 🕹 Como Executar e Testar
1. Com as credenciais configuradas, clique em **Execute Workflow** ou ative o nó de trigger.
2. No Telegram, inicie uma conversa com seu bot.
3. Envie o nome de uma cidade e estado no formato: `Cidade, UF` (ex: `Curitiba, PR`).
4. **Retorno esperado:** Você receberá uma mensagem como: *"🌤 A temperatura em Curitiba é de 18°C"*.
5. **Teste de erro:** Caso envie uma cidade inexistente ou formato inválido, o bot responderá com uma mensagem de orientação.

---

### ⚠️ Avisos de Segurança
*   **Não inclua segredos reais:** Verifique se o arquivo JSON exportado ou este README não contêm seus tokens ou chaves de API reais.
*   **Repositório Público:** Este repositório deve permanecer público para fins de avaliação.

***

**Observação:** Lembre-se de que, conforme as fontes, é fundamental garantir que nenhum token real seja enviado para o GitHub para manter a segurança das suas contas.
