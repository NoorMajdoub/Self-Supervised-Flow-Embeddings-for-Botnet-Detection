core concept : self learning in cybersec

resources
Online Self-Supervised Deep Learning for Intrusion Detection Systems
https://arxiv.org/abs/2306.13030


-------------
why use of embeddings instead of raw data (the bytes , packets ) the regular tabular :
first of all how ? : you have tabular data right ? with labels for what each feature is 
we can be working with each feature indep and just remove the labbel , here we have unsupervised learning but we are doing self supervised 
why embed can be better than working with each feature alone:
high dimensions , many features
Embeddings enable generalization and few-shot detection

SimCLR :
not a model itself but the concept , you take your raws of data and for each find ways to create different views of it , pass then to encoder to get the embeddings
