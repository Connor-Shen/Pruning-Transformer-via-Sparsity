# Pruning-Transformer-via-Sparsity

Neural network pruning is a method that revolves around the intuitive idea of removing superfluous
parts of a network that performs well but costs a lot of resources. Indeed, even though large neural
networks have proven countless times how well they could learn, it turns out that not all of their parts
are still useful after the training process is over. The idea is to eliminate these parts without impacting
the network’s performance.
![img](https://github.com/Connor-Shen/Pruning-Transformer-via-Sparsity/blob/main/img/gradual.png)

## Vision Transformer(vit) and Sparsity
![img](https://github.com/Connor-Shen/Pruning-Transformer-via-Sparsity/blob/main/img/vit_figure.png)
Despite the impressive empirical performance, ViTs are generally heavy to train, and the trained
models remain massive. That naturally motivates the study to reduce ViT inference and training
costs. As a result, chasing sparsity in Vision Transformers was crucial. The most common type of
sparse regularization is l1 sparsity , which has been incorporated into neural networks and applied to
network pruning . Besides, structural sparsity (including group sparsity, and layer sparsity) was also
presented. Recently, it has been applied to prune the transformer, by exploiting different candidates
for pruning (including pruning multiple heads, and pruning the tokens).

## Sparse Vision Transformer Exploration

![img](https://github.com/Connor-Shen/Pruning-Transformer-via-Sparsity/blob/main/img/structure.png)
Our proposed techniques was mainly inspired by [Zhu et al. [2021], Chen et al. [2021]](check detail in report). It starts from
a randomly sparsified model; after optimizing several iterations, it shrinks a portion of parameters
based on pre-defined pruning criterion(e.g. weight magnitude), and activates new connections. After
upgrading the sparse topology, it trains the new subnetwork until the next update of the connectivity.

### Heatmap of Attention probabilities for DeiT-Base and SViTE-Base with 40% Sparsity
<div style="display:inline-block">
  <img src="https://github.com/Connor-Shen/Pruning-Transformer-via-Sparsity/blob/main/img/heatmap_base.png" alt="image1" width="200">
  <img src="https://github.com/Connor-Shen/Pruning-Transformer-via-Sparsity/blob/main/img/heatmap_sparse.png" alt="image2" width="200">
</div>
