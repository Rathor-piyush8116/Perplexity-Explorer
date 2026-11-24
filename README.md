# Perplexity Explorer

An interactive web application demonstrating how language models evaluate sentence probability and compute **Perplexity**.

## Features

1. **Sentence Perplexity Evaluation**:
   - Type any custom sentence or pick from quick presets (*"I love Python"*, *"Python love I"*, *"The capital of France is Paris"*).
   - Generates token-by-token conditional probabilities $P(\text{token}_i \mid \text{context})$.
   - Highlights token probability with intuitive color coding (green for expected words, amber for moderate, red for surprising/improbable words).

2. **Step-by-Step Mathematical Breakdown**:
   - **Step 1:** Multiply all reciprocal probabilities: $\prod_{i=1}^N \frac{1}{P(\text{token}_i)}$
   - **Step 2:** Count the total tokens $N$.
   - **Step 3:** Take the $N$-th root to get the geometric mean:
     $$\text{Perplexity} = \left(\prod_{i=1}^N \frac{1}{P(\text{token}_i)}\right)^{\frac{1}{N}}$$
   - Plain-English interpretation of perplexity as the model's effective branching factor (uncertainty).

3. **Interactive "Try it by hand" Calculator**:
   - Fully customizable token and probability list.
   - Live real-time updates as you type or change probabilities.
   - Educational presets:
     - *"I love Python (0.5, 0.8, 0.2)"*
     - *"All 1/8"* (demonstrating why uniform $P=0.125$ yields exactly $\text{PPL} = 8$)
     - *"One surprising word"* (demonstrating how a single rare word spikes perplexity)

## How to Run

Simply open `index.html` in any modern web browser:

```bash
# On macOS:
open index.html

# Or run a local HTTP server:
python3 -m http.server 8000
# Then visit http://localhost:8000
```
