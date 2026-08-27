# Embeddings: Representing Meaning as Vectors

**Date:** 2026-08-26  
**Tags:** #embeddings #vector-search #rag

## What I learned

Embeddings convert text into numerical vectors: long lists of numbers that represent semantic meaning.

The individual numbers do not have human-readable meanings. Instead, an embedding's meaning comes from its position and direction relative to other embedding vectors.

Texts with similar meanings, such as "reset my password" and "forgot my login details," should produce vectors that point in similar directions.

## Cosine similarity

Cosine similarity is a mathematical concept from linear algebra. It measures the angle between two vectors:

- Close to `1`: vectors point in similar directions.
- Close to `0`: vectors are less related.
- Close to `-1`: vectors point in opposite directions.

Cosine similarity does not make similar text point in the same direction. It only measures the similarity between vectors that an embedding model has already produced.

## How embedding models learn meaning

Embedding models are trained on a large amount of language data. During training, the model adjusts its internal weights so related text gets vectors that are close together, while unrelated text gets vectors farther apart.

For example:

- **Query:** "How do I recover my account?"
- **Relevant text:** "Instructions for resetting a password"
- **Unrelated text:** "How to make pasta"

The model learns that the query and relevant text should have a higher cosine similarity.

## How this supports vector search

1. Split documents into smaller chunks.
2. Convert each chunk into an embedding vector.
3. Store each vector with its original text and metadata.
4. Convert the user's question into an embedding using the same model.
5. Compare the question vector with stored vectors.
6. Return the most similar chunks.

## Important takeaway

Embeddings enable semantic search: finding text based on meaning rather than exact keyword matches.

## Questions to explore next

- How are embedding models trained in more detail?
- What is the difference between cosine similarity and Euclidean distance?
- How should documents be chunked before creating embeddings?
- What embedding model should I use for a small RAG project?
- How do vector databases efficiently find nearest vectors?
