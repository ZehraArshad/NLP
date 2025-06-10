# How do Transformer work?

### Neural Networks

- Backend has a simple neural network


## Working and Architecture

### Input
- Novel part is positional embedding which is an addition to the trad embedding that didn't care about the word's position. 

### Multi-head attention
- What is the relevance of one word to another?
- Like what are the chances of 'the' appearing with 'my'?
- This was done through calculating its attention score

## Timm Library

- PyTorch Image Models ( timm ) is a collection of image models, layers, utilities, optimizers, schedulers, data-loaders / augmentations, and reference training / validation scripts that aim to pull together a wide variety of SOTA models with ability to reproduce ImageNet training results.

- Efficient for fast model dev 


### How to get compute fo building these models?

- gpus (hugging face)

### How to decide on model?
- Look for usecase on HF
- Use it as is
- Else, fine tune
- Last option is to make your own model

### Can I use this model on my pc (cpu)?

- multiply billion par of model with 2 
- If you have that much space, then yes
- Else, you can download it but can't run it
- If there are 4bil params then it will consume ~ 8.6 gbs