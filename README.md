
# Self-Supervised Representation Learning Project

This project explores **self-supervised learning** techniques for image representations using BYOL, SimCLR, and a hybrid approach combining both. We evaluate the learned embeddings on a downstream classification task.

## Implemented Methods

1. **BYOL (Bootstrap Your Own Latent)**

   * Two augmented views of the same image.
   * Online network: encoder → projector → predictor.
   * Target network: encoder → projector.
   * Loss aligns the online predictor output with the target projector output (cosine similarity).

2. **SimCLR**

   * Two augmented views of each image passed through the same encoder + projector.
   * NT-Xent contrastive loss is applied to maximize similarity between positive pairs and push apart negatives.

3. **Hybrid BYOL + Contrastive**

   * Online predictor output aligned with target projector (BYOL loss).
   * Simultaneously, contrastive loss applied to embeddings (projector or predictor) across the batch to improve discriminative power.

## Downstream Evaluation

* Trained a **linear classifier** on the embeddings to test representation quality.
* Dataset used: **CTU-13** (unsupervised pretraining, linear evaluation protocol).



If you want, I can also write a **super-short 5–6 line version** suitable for GitHub so it’s even more “readable at a glance.” Do you want me to do that?
