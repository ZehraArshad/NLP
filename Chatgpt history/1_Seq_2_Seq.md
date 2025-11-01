### Problem
Sequences pose a challenge for DNNs because they require that the dimensionality of the inputs and
 outputs is known and fixed. 

 ### Solution 

 The idea is to use one LSTM to read the input sequence, one timestep at a time, to obtain large fixed
dimensional vector representation, and then to use another LSTM to extract the output sequence
 from that vector.

### Inspiration
 Our approach is closely related to Kalchbrenner and Blunsom who were the first to map the entire input sentence to vector, and is related to Cho et al. Although, the latter was used only for rescoring hypotheses produced by a phrase-based system.

 ### Optimization 
 Note that the LSTM reads the  input sentence in reverse, because doing so introduces many short term dependencies in the data that make the optimization problem much easier.

### History
  The RNN can easily map sequences to sequences whenever the alignment between the inputs the
 outputs is known ahead of time. However, it is not clear how to apply an RNN to problems whose
 input and the output sequences have different lengths with complicated and non-monotonicrelation
ships.

### This paper's approach

RNN (english) - vector - RNN (french) 
❗fails for longer sentences (temporal dependencies) 
- Instead, use two lstms (inc params at negligible cost, and good for simultaneously training on multiple langs)
- deep lstms (4 layers) are used because they are better than shallow
- instead of *a,b,c to alpha, beta gamma* it uses *c,b,a to alpha beta gamma* because a is near to alpha, this supports sgd to establish communication between input and output. *alpha beta gamma is translation of a, b, c*

### Model Arch

LSTM - 4 layers
\
Each layer - 1000 cells
\
Word embeddings - 1000 word embeddings
\
Input vocab - 160,000
\
Output vocab - 80,000

### Dictionary 

| Word | Meaning |
|---|---|
|SMT Statistical Machine Translation | uses stat models to find patterns in large bilingual text corpora