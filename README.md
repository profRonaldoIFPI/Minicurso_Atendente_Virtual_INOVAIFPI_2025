# Minicurso_Atendente_Virtual_INOVAIFPI_2025

Conteúdo do minicurso: construir um Atendente Virtual fundamentado em documentos (RAG) usando a API Gemini.

Arquivos principais
- Notebook de referência: `Chat bot baseado em texto.ipynb`

Resumo
- Objetivo: criar um chatbot que responda apenas com base em documentos indexados (PDF/TXT), evitando "alucinações".
- Arquitetura RAG: Indexação → Recuperação → Geração.
  - Indexação: ingestão de PDFs/TXT, divisão recursiva em chunks, geração de embeddings.
  - Recuperação: embedding da consulta (`RETRIEVAL_QUERY`) e busca por similaridade em um vector store.
  - Geração: prompt engineering para forçar o modelo a usar somente o contexto recuperado (Gemini).

Dependências
- google-generativeai
- pypdf
- langchain-text-splitters
- chromadb

Instalação (exemplo)
```bash
pip install -U google-generativeai pypdf langchain-text-splitters chromadb
```

Configuração da API
- Defina a chave da API Gemini no notebook:
  - Exemplo rápido (não recomendado em produção):
    ```python
    GOOGLE_API_KEY = "SUA_API_KEY_AQUI"
    ```
  - Recomenda-se usar variáveis de ambiente ou dotenv (.env) para proteger a chave.
  - No Google Colab o notebook mostra uso alternativo com `userdata` para demonstrar.

Estrutura e execução
1. Coloque os documentos (PDF/TXT) em `content/` (uso relativo no notebook).
2. Execute as células do notebook para:
   - Ingerir e extrair texto (pypdf).
   - Dividir texto em chunks (RecursiveCharacterTextSplitter).
   - Gerar embeddings com `google-generativeai`.
   - Armazenar embeddings no ChromaDB (`./chroma_db` por padrão).
   - Fazer consultas: gerar embedding da query, recuperar chunks relevantes e montar prompt RAG.
   - Gerar resposta com o modelo Gemini configurado no notebook.

Links úteis
- ChromaDB: https://www.trychroma.com/
- FAISS (alternativa): https://ai.meta.com/tools/faiss/
- Exemplo de documento usado: Organização Didática do IFPI (link no notebook)

Notas de segurança
- Nunca comite sua API Key no repositório.
- Para deploy ou produção, proteja credenciais e aplique controle de acesso.

Uso rápido
- Abra `Chat bot baseado em texto.ipynb` no Jupyter/VSCode/Colab e siga as instruções nas células.