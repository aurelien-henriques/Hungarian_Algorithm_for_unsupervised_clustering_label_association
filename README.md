# Hungarian_Algorithm_for_unsupervised_clustering_label_association
This package development in RCPP is useful for a concrete application of hungarian algorithm to weakly labeled datasets resolution: 

The hungarian algorithm is a O(n^4) algorithm which aims at solving an assignation problem between tasks and workers by minimizing a cost. Each task/worker assignation is stored in a coefficient of a cost matrix of length number of task per number of worker, and the sum of all assignations is the one that has to be optimized.

In an algorithmic project with Willy Kinfoussia, we developped a R/RCPP package that manages to find the right association between clusters of points in a dataset and labels of certain points of the same dataset. To be clear, we proposed a way to:

- Calculate an eculidean distance in a reduced dimension between mass center of a cluster and mass center of all labeled data that have the same label
- Store the cost in a matrix for each couple of cluster/label
- Compute through hungarian algorithm the optimized assignation between each cluster and each type of label

Exemple: For N=10000 unlabeled data and N=50 labeled data in 5 labels, we would like to give a label to the unlabeled data using the available data. We can reduce dimensionnality of data, use any unsupervised clustering to cluster the unlabeled data, compute their mass center then compute the mass center of all labeled data for each label. Then we use euclidean distance between mass centers of clusters and mass centers of labeled data to obtain a cost matrix. Our package then uses hungarian algorithm to find the right association, which gives a label for each unlabeled cluster, thus giving a label to unlabeled data. 
