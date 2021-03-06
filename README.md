# KMD hierarchical clustering
Clustering method based on hierarchical agglomerative clustering with KMD linkage

 ## Requirments 
Python: versions 3.6.5 and 3.7. We don't expect this to work with Python 2.x

Packages: scipy, numpy, matplotlib

## Getting Started
Download the project to your work directory:
```
git clone https://github.com/avivzelig/KMDHierarchicalClustering.git
```

## Usage in Python enviorment 

```
from KMDHierarchicalClustering.KMDclustering.KMDAlgo import KMDLinkage
```

- Parameters to specify:

  X- dataset to cluster
  
  k- number of minimum distances used to calculate distance between clusters. if flag is compute, best k will be predicted.
  
  n_clusters- number of clusters
  
  min_cluster_size- the minimum number of points that can be in a cluster,if cluster is smaller then this size it is considered as an outlier
  
  
- Parmaters that are recomemded to use as defult:

    affinity- Metric used to compute the distance. Can be “euclidean”, “correlation”, "spearman",“precomputed",'compute'
    or any metric used by scipy.spatial.distance.pdist.If “precomputed”,a distance matrix (instead of a similarity matrix) is needed as input for the fit method
    If “compute” flag is used, algorithem will decide based on dataset size 

    certainty- parameter indicating how certain the algorithm is in the correctness of its classification in the outlier hanging step, if 0.5 - all outliers will be       hanged if 1 - outliers will not be hanged

    k_scan_range-(tuple) the range of k's used to search for k.(start k, stop k, jumps)

    y_true- cluster True labels

    plot_scores- if True, a plot of intrinsic score vs extrinsic score on different k's will be ploted, True labels

    path- path to self prediction for each k , if False - prediction will not be saved
    will be required
 
## Usage example
  
```
KMDLinkage(X, k='compute', n_clusters = 2, min_cluster_size = 10)
```



