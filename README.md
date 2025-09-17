# NLP Tokenization Playground

Compare four tokenization strategies — character-level, word-level, phrase-level (bigrams), and subword tokenization via Byte‑Pair Encoding (BPE) — and see how each affects vocabulary size and average sequence length.

## Features
- Minimal preprocessing (lowercasing, newline→space)
- Character-, word-, phrase-level (top‑N bigram merges), and a simple BPE trainer/encoder
- Evaluation of vocabulary size and average tokens per sentence
- Scatter plot visualization of the trade‑off

## Files
- `tokenization.ipynb`: Main notebook with all implementations and evaluation
- `sample_text.txt`: Sample corpus (public‑domain excerpt from Alice's Adventures in Wonderland)

## Requirements
- Python 3.10+ (3.12 tested)
- Jupyter (or VS Code/Cursor/JupyterLab)
- matplotlib

You can install Jupyter and matplotlib with:
```bash
pip install jupyter matplotlib
```

## Quick start
1. Ensure `sample_text.txt` is in the same directory as `tokenization.ipynb`.
2. Open the notebook and run all cells.
3. The notebook will:
   - Preprocess the text
   - Tokenize using character, word, phrase (top‑5 bigrams), and BPE (trained with `num_merges=50`)
   - Print metrics and render a scatter plot (vocab size vs. average sequence length)

## Results (example)
Your exact numbers will vary by corpus and parameters, but you should observe roughly:
- Character: very small vocabulary, longest sequences
- Word: large vocabulary, shorter sequences
- Phrase (bigrams): slightly shorter sequences than word with a modest vocab increase
- BPE: balanced vocabulary size with moderate sequence length and robust OOV handling

## Notes
- Phrase merging uses the top‑N bigrams (N=5 by default). Increasing N typically shortens sequences but increases vocabulary.
- BPE here is a simple educational implementation; production tokenizers add many details (merges serialization, special tokens, caching, etc.).

## Attribution
- The sample text is adapted from a public‑domain edition of “Alice’s Adventures in Wonderland” (Chapter 1). If you publish results, please credit the source and confirm your excerpt’s public‑domain status in your jurisdiction.

## License
Add a license file (e.g., MIT) if you plan to share this repository publicly. 