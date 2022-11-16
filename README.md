# UPGMA_algorithm
UPGMA: Unweighted Pair Group Method with Arithmetic Mean: A simple clustering method that assumes a constant rate of evolution (molecular clock hypothesis). 
It needs a distance matrix of the analysed taxa that can be calculated from a multiple alignment.


.     UPGMA starts with a matrix of pairwise distances D[1..n, 1..m].
·     In the following text each sample (taxon, operational taxonomic unit=OTU) is denoted as a 'cluster'.
·     starts by assigning all clusters (samples) to a star-like tree.


# ALGORITHM
1.   Find that pair (cluster i and j) with the smallest distance value in the distance matrix: D[i,j].
2.   Define a new cluster comprising cluster i and j:
Cluster i is connected by a branch to the common ancestor node. The same applies for cluster j.
Therefore, the distance D[i,j] is split onto the two branches. So, each of the two branches obtains a length of D[i,j]/2.
3.   If i and j were the last 2 clusters, the tree is finished. If not the algorithm finds a new cluster called u.
4.   Define the distance from u to each other cluster (k, with k <> i or j) to be an average of the distances dki and dkj.
For 'Weighted PGMA (WPGM)': dku = dki+dkj/2).
For 'Complete linkage': dku = max(dki, dkj).
For 'Single linkage': dku = min(dki, dkj).
5.   Go back to step 1 with one less cluster. Clusters i and j are eliminated, and cluster u is added to the tree.
