## Problem statement

The goal is to train a Roberta Model to predict the sentiment of movie reviews on the Internet Movie Review Database (IMDB).

## Solution

In this study I have used the Roberta model developed by Liu et al at Facebook AI. As the revolutionary BERT model created by Devlin et al had been trained on two primary objectives i.e (i) Masked Language Modeling objective and (ii) Next Sentence Prediction objective, Roberta affixes and supersedes the performance of previously established benchmarks by removing the NSP objective and training with much larger mini batch sizes and learning rates. Roberta uses the ubiquitous transformer architecture by Vaswani et al. It consists of an encoder stack of L layers. Each block uses A self-attention heads and hidden dimension H.

The pretrained model was loaded from Hugging Faces' `transformers`. Then a classification linear layer was appended to the encoder output. When input tokenized ids of text are passed through RoBERTa then it outputs a representation (also called embedding in this case). This representation is then passed through encoder and subsequent classification layers. Following the output activations from the encoder is extracted and then passed through a logistic classifier (using `nn.Linear` module). Following this we train the model using `nn.CrossEntropyLoss` loss.

### Future work

1. Training the |Roberta model appended by an LSTM classifier or a GRU classifier
2. The model can be trained longer to see if the accuracy improves further.
3. One can choose to train some other recent SOTA Transformer models such as Longformer, Electra, etc. for sentiment classification.

## Results

Train accuracy: 94.61%

Train loss: 0.17

Validation accuracy: 92.17%

Validation loss: 0.27