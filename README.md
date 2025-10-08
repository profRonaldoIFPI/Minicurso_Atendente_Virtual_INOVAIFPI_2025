# Minicurso_Atendente_Virtual_INOVAIFPI_2025

## Conteúdo do Minicurso: Atendente Virtual com IA (RAG + Gemini)

Este repositório reúne o conteúdo do Minicurso de Atendente Virtual com IA (INOVAIFPI 2025), baseado no notebook de referência em Chat bot RAG.ipynb.

- Objetivo: construir um chatbot fundamentado em documentos, usando RAG + API Gemini, com respostas precisas e rastreáveis.
- Arquitetura (RAG): Indexação → Recuperação → Geração.
  - Indexação: ingestão (PDF/TXT), divisão recursiva de texto (chunks), embeddings (text-embedding-004).
  - Recuperação: embedding da consulta com `RETRIEVAL_QUERY` e busca por similaridade (cosseno).
  - Geração: engenharia de prompt restrita ao contexto recuperado e resposta via Gemini.
- Dependências: `google-generativeai`, `pypdf`, `langchain-text-splitters`, `chromadb`.
- Vetor store: recomendação de [ChromaDB](https://www.trychroma.com/) (alternativa [FAISS](https://ai.meta.com/tools/faiss/)).
- Corpus de exemplo: [Organização Didática do IFPI](https://www.ifpi.edu.br/acesso-a-informacao/institucional/consuprn1432022organizacaodidatica.pdf).

### Passos rápidos
1. Defina `GOOGLE_API_KEY`.
2. Instale as dependências e execute o notebook.
3. Adicione seus documentos ao `ChromaDB` e faça consultas.

Projeto de Atendente Vitual com IA desenvolvido no Minicurso do INOVAIFPI_2025
