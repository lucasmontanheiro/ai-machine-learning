# Retrieval Augmented Generation (RAG)

A tidy RAG pipeline

1) **Ingest & normalize** (essential): Pull data (TSV/CSV/HTML/PDF), clean types, fix encodings, unify schema.
2) **Chunk / segment** (essential): Decide unit of retrieval (row, paragraph, section). Avoid over-long chunks; keep facts that belong together in the same chunk.
3) **Add metadata & IDs** (essential): Store source URL, row ID, timestamps, tags. You’ll use this for filtering, citations, and updates.
4) **Embed** (essential): Create vectors for each chunk with an embedding model.
5) **Index** (essential): Write vectors to a store (FAISS/Chroma/Qdrant/etc.). Optionally also index text for hybrid search (BM25 + vectors).
6) **Query processing** (optional but helpful): Rewrite/expand the user question (synonyms, typo fix, filters, date hints).
7) **Candidate retrieval** (essential): Search the index and get top-k candidates (start with k≈3–5).
8) **Re-rank / filter** (optional, strong upgrade): Use a cross-encoder or lightweight LLM pass to re-order the k, drop low-similarity items, and de-duplicate.
9) **Context assembly** (essential): Concatenate the top snippets with provenance, enforce token budget, maybe compress/summarize long bits.
10) **Generation** (essential): Prompt the LLM to answer only from context; include instructions for citation/refusal if unsupported.
11) **Grounding, citations, and refusals** (essential): Show sources; if nothing strong found, say “don’t know” instead of guessing.
12) **Post-processing** (optional): Format tables, units, JSON output, highlights.
13) **Feedback, refresh & ops** (optional but important in practice): 
- Re-embed only changed rows (hashing).
- Track metrics (latency, cost, hit rate, precision@k): 
- Cache frequent Q→A.
- Guardrails (PII, policy filters).


## RAG's with TXT/PDF
- Add link to github: colab with OpenAI

## RAG's with Spreadsheet Data
- Add link to github: colab with Google Sheet data
- How your TSV gets turned into “chunks”: When we load your Google Sheet TSV, the chunk creation step typically does:
```
chunk_text = f"Column1: {value1} | Column2: {value2} | Column3: {value3}"
```

- If each row is kept as one chunk, then yes — RAG will preserve the relationships between values in the same row and the same columns, so the LLM can reason across them naturally.