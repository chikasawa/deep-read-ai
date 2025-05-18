# Deep Read AI

![Deep Read AI](docs/img/036936d122dcb85e96fe1b0b9751ecb67affce201fc4a8f3d2621ebc90dc6f43.png)

Deep Read AI é um sistema inteligente que não apenas salva links, mas realiza uma leitura profunda do conteúdo utilizando Inteligência Artificial. O projeto foi desenvolvido com o apoio da Alura e Google Gemini.

## 🚀 Visão Geral

O sistema Deep Read AI automatiza o processo de leitura e compreensão de conteúdo web através de uma combinação de ferramentas modernas:

- **N8N**: Workflow de automação low-code
- **KaraKeep**: Gerenciamento de bookmarks
- **Google Gemini**: Inteligência Artificial para processamento de texto
- **Pinecone**: Banco de dados vetorial para armazenamento de embeddings
- **Telegram**: Interface de usuário para interação

## 📊 Banco de Dados Vetorial

O Pinecone, nosso banco de dados vetorial, é uma peça fundamental do sistema. Ele funciona da seguinte maneira:

### O que são Vetores?
- Vetores são representações numéricas de texto ou conteúdo
- Cada vetor captura o significado semântico do conteúdo
- Vetores similares representam conteúdos semanticamente relacionados

### Como Funciona no Deep Read AI
1. **Geração de Embeddings**: O Google Gemini converte o conteúdo dos bookmarks em vetores
2. **Armazenamento**: Os vetores são armazenados no Pinecone
3. **Busca Semântica**: Quando um usuário faz uma consulta:
   - A consulta é convertida em vetor
   - O Pinecone encontra os vetores mais similares
   - Retorna os conteúdos mais relevantes semanticamente

### Vantagens
- Busca por significado, não apenas palavras-chave
- Encontra conteúdo relacionado mesmo com palavras diferentes
- Permite consultas em linguagem natural
- Alta performance em buscas semânticas

## 🔄 Workflows

### 1. Processamento de Novos Bookmarks

Quando um novo bookmark é adicionado no KaraKeep:
1. O webhook do KaraKeep é acionado
2. O conteúdo é processado pelo Google Gemini para gerar embeddings
3. Os dados são armazenados no Pinecone para consultas futuras

### 2. Consulta via Telegram

Os usuários podem:
- Consultar informações sobre bookmarks salvos
- Receber insights e resumos do conteúdo
- Interagir com o sistema através de comandos simples

## 🛠️ Instalação e Configuração

### N8N
- [Site oficial](https://n8n.io/)
- [Documentação de instalação](https://docs.n8n.io/hosting/)
- [Guia de webhooks](https://docs.n8n.io/workflows/components/nodes/n8n-nodes-base.webhook/)

### KaraKeep
- [Site oficial](https://karakeep.com/)
- [Documentação de API](https://karakeep.com/docs/api)
- [Configuração de webhooks](https://karakeep.com/docs/webhooks)

### Google Gemini
- [Google AI Studio](https://makersuite.google.com/app/apikey)
- [Documentação da API](https://ai.google.dev/docs)
- [Guia de embeddings](https://ai.google.dev/docs/embeddings_guide)

### Pinecone
- [Site oficial](https://www.pinecone.io/)
- [Documentação](https://docs.pinecone.io/)
- [Guia de início rápido](https://docs.pinecone.io/docs/quickstart)

### Telegram Bot
- [Documentação do Bot API](https://core.telegram.org/bots/api)
- [Guia de criação de bot](https://core.telegram.org/bots/tutorial)

## 📸 Screenshots dos Workflows

### Interface do Karakeep para adicionar um novo Bookmark
![Interface Karakeep](docs/img/Screenshot%202025-05-17%20at%2022.47.57.png)

### Workflow de Processamento de Bookmarks
![Workflow de Processamento de Bookmarks](docs/img/Screenshot%202025-05-17%20at%2022.51.25.png)

### Workflow de Consulta via Telegram
![Workflow de Consulta via Telegram](docs/img/Screenshot%202025-05-17%20at%2022.51.56.png)

### Interface do Telegram
![Interface do Telegram](docs/img/Screenshot%202025-05-17%20at%2023.20.46.png)

## 🎥 Demonstração em Vídeo

### Workflow de Processamento de Bookmarks
https://github.com/user-attachments/assets/ffdf238a-01ec-4f70-aabe-3a16f1c3223f

### Workflow de Consulta via Telegram
https://github.com/user-attachments/assets/b1841a51-8c3e-45b1-a3d0-832d04adc10e

## 🤖 Prompt Engineering

O sistema utiliza um prompt específico para otimizar a interação com o usuário via Telegram. Este prompt foi cuidadosamente elaborado para garantir respostas precisas e úteis na recuperação de bookmarks.

### Estrutura do Prompt

O prompt define um assistente especializado em recuperação de bookmarks com as seguintes características:

1. **Função Principal**
   - Receber consultas dos usuários
   - Buscar no banco de dados vetorizado
   - Criar resumos sintéticos
   - Apresentar lista ordenada de resultados

2. **Formato de Resposta**
   - Resumo sintético com referências bibliográficas
   - Lista ordenada de bookmarks com:
     - Título
     - Descrição
     - URL
     - Relevância
     - Categoria (quando disponível)

3. **Tratamento de Contexto**
   - Priorização por data
   - Peso para palavras-chave
   - Refinamento de busca com informações parciais

4. **Diretrizes de Interação**
   - Clareza nas respostas
   - Sugestões de refinamento
   - Tratamento de limitações
   - Fluxo de interação estruturado

### Exemplos de Interação

O prompt inclui exemplos práticos de interação, demonstrando:
- Consultas sobre tópicos específicos
- Busca por materiais recentes
- Tratamento de diferentes tipos de consultas

### Metadados Utilizados

Para cada bookmark, o sistema processa:
- Título
- URL
- Descrição
- Categoria (quando disponível)

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
