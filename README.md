## Qualitative and Quantitative Analysis of Dimesionality Reduction Methods

We analyed 3 dimensionality reduction methods namely Principal Component Analysi (PCA), Uniform Manifold Approximation and Projection (UMAP) and t-Distributed Stochastic Neighbor Embedding (t-SNE)​.

1. **PCA** is a linear dimensionality reduction technique that can be viewed as an algorithm trying to find a way to reconstruct the data as a linear combination of a small number of prototypes.
2. **UMAP** is a non-linear dimensionality reduction technique that can be seen as a graph based algorithm where a low dimensional representation is built, that gives a graph that matches as closely as possible to the graph built in high dimensional case. It uses the KL divergence loss function to project the high dimensional probability to low dimensional probability and then minimizes this loss using the gradient descent optimisation.
3. **t-SNE** is a t-SNE like non-linear dimensionality reduction technique with a more firm mathematical foundation. It uses the binary cross-entropy loss function instead of the KL divergence function as in t-SNE. The additional second term of this loss function enables UMAP to capture the global structure of the data which t-SNE cannot. Also, unlike t-SNE, UMAP does not apply normalisation to the probability distribution of the low or high dimensional points. This absence of normalisation, drastically reduces the computation time.

We tested these dimensionality reduction methods on 3 datasets - MNIST digit dataset, Fashion-MNIST dataset and the Breast Cancer Wisconsin Diagnostic dataset. In terms of quantitative metrics, used the time complexity, normalized mutual score and the stability of sub-sample embeddings to assess the performance of the algorithms. 

Our analysis concludes that t-SNE is much more computationally intensive than UMAP and the latter is preferred as it produces the same (rather better) results than tSNE in less time. In case of normal mutual information, UMAP(0.70 for normalized data) has a slightly higher value than tSNE(0.59), signifying that the reduced embeddings are more strongly correlated to the initial input data in case of UMAP which is more desirable. While comparing the stability of UMAP and tSNE based on Normalised Procrustes distance, UMAP performed better as its sub-sample embeddings were more similar to that of the full dataset.

For qualitative analysis, we looked into the performance of both tSNE and UMAP for in terms of varying dataset size and varying number of features in the dataset (i.e. performance on high dimension data). For both metrics, UMAP algorithm performed much more efficiently.

Finally it was concluded that UMAP is the most efficient algorithm among the three dimensionality reduction methods.

---

Note: The python notebooks contains the code we used to generate the quantative metrics.
