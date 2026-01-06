# 📚 RAG Workshop: Understanding Retrieval-Augmented Generation

Welcome to this hands-on workshop on **Retrieval-Augmented Generation (RAG)**!

## 🤔 What is RAG?

**RAG** combines the power of:
1. **Retrieval** - Finding relevant information from a knowledge base
2. **Augmentation** - Adding that information to your prompt
3. **Generation** - Using an LLM to generate responses with context

```
┌─────────────────────────────────────────────────────────────────┐
│                        RAG Pipeline                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   User Query                                                     │
│       │                                                          │
│       ▼                                                          │
│   ┌─────────────────┐    ┌─────────────────────────────────┐    │
│   │ Embed Query     │───▶│ Search Vector Database          │    │
│   │ (Text → Vector) │    │ (Find Similar Embeddings)       │    │
│   └─────────────────┘    └─────────────┬───────────────────┘    │
│                                        │                         │
│                                        ▼                         │
│                          ┌─────────────────────────────────┐    │
│                          │ Retrieved Documents             │    │
│                          │ (Top-K Most Relevant)           │    │
│                          └─────────────┬───────────────────┘    │
│                                        │                         │
│                                        ▼                         │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │ Augmented Prompt = Query + Retrieved Context            │   │
│   └─────────────────────────────────┬───────────────────────┘   │
│                                     │                            │
│                                     ▼                            │
│                          ┌─────────────────────────────────┐    │
│                          │ LLM Generates Response          │    │
│                          │ (With Knowledge Context)        │    │
│                          └─────────────────────────────────┘    │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## 🎯 Workshop Objectives

By the end of this workshop, you will understand:
- How words/sentences are converted to **embeddings** (vectors)
- How **similarity** is measured between embeddings
- Why different **embedding models** produce different results
- The foundation for building RAG systems

## 📓 Workshop Notebooks

| Notebook | Description |
|----------|-------------|
| `01_embedding_visualization.ipynb` | Visualize word embeddings in 3D space + Cosine similarity heatmap |
| `02_model_comparison.ipynb` | Compare how different embedding models represent the same words |
| `03_multilingual_comparison.ipynb` | **NEW!** Compare Thai support: what happens with unsupported languages? |

## 🚀 Getting Started

### Option 1: Google Colab (Recommended)
1. Upload notebooks to Google Colab
2. Run each cell from top to bottom
3. Dependencies are installed automatically

### Option 2: Local Environment
```bash
pip install -r requirements.txt
jupyter notebook
```

## 📦 Dependencies

- `sentence-transformers` - Pre-trained embedding models
- `plotly` - Interactive 3D visualizations
- `seaborn` - Beautiful heatmaps
- `scikit-learn` - t-SNE dimensionality reduction
- `numpy`, `pandas` - Data manipulation

## 🔑 Key Concepts

### Embeddings
Embeddings convert text (words, sentences, documents) into numerical vectors. Similar meanings = similar vectors!

### Cosine Similarity
Measures the angle between two vectors. Range: -1 to 1
- **1.0** = Identical direction (most similar)
- **0.0** = Perpendicular (unrelated)
- **-1.0** = Opposite direction (most dissimilar)

### t-SNE
A technique to visualize high-dimensional data (768+ dimensions) in 2D or 3D while preserving relative distances.

---

Happy Learning! 🎉
