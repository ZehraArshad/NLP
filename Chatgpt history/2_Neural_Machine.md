### background

- Most MT depend on enc/dec 
- But, not in this paper
- As length of sentence increases, the performance of enc/dec decreases because they need a fixed length vector after the encoding


### Solution 
🧭 1. Attention Mechanism

Instead of relying on a single final hidden vector, the decoder learns to “attend” to different parts of the input sequence while generating each output word.

So at each decoding step:

The model looks back at all encoder states.

It computes attention weights to decide which input words are most relevant right now.

Then it forms a context vector dynamically for that step.

This solved the bottleneck problem — now, longer sentences could be handled much better, and translations became far more accurate and fluent.

🧩 2. End-to-End Training for Alignment

The attention mechanism also learned soft alignments between source and target words as part of training, replacing the hand-crafted alignment heuristics of earlier SMT systems.

### Inspiration 

-  Learning phrase representations using RNN encoder-decoder for statistical machine translation
- Sequence to sequence learning with neural networks


- It clearly shows below how a certain word in translation depend on a certain word in original sentence
![alt text](image-10.png)

