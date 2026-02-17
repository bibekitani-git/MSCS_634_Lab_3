# MSCS 634 Lab 3: Clustering Analysis Using K-Means and K-Medoids Algorithms

## Purpose
This lab explores unsupervised learning by applying K-Means and K-Medoids clustering algorithms to the Scikit-learn Wine dataset. The objective is to evaluate how each algorithm partitions data based on chemical properties and to compare their effectiveness using Silhouette Scores and the Adjusted Rand Index (ARI).

## Key Insights
* **Metric Analysis:** * **K-Means** typically achieved a higher **Silhouette Score**, indicating that it creates more cohesive, well-separated clusters by minimizing squared Euclidean distance.
    * **K-Medoids** provided a more robust representation because the cluster center is an actual data point (a "medoid") rather than a mathematical average.
* **Effect of Scaling:** Standardizing the dataset via Z-score normalization was essential. Without it, high-magnitude features like 'Proline' would have disproportionately influenced the distance calculations.
* **Visualization:** Using PCA to reduce the 13-dimensional feature space to 2D allowed for a clear visual comparison. While the clusters overlap slightly, both algorithms successfully identified the three primary categories of wine.

## Challenges & Decisions
* **Custom Implementation:** Due to environment shell restrictions preventing the installation of `scikit-learn-extra`, I implemented a **Custom K-Medoids approach**. I utilized K-Means to find initial centroids and then mathematically identified the actual data observations closest to those centers to serve as the Medoids.
* **Metric Choice:** Adjusted Rand Index (ARI) was used alongside the Silhouette Score to measure how closely the unsupervised clusters aligned with the known ground-truth labels of the dataset.

## How to Run
1. Open the `Lab_3_Clustering.ipynb` in any Jupyter environment.
2. Ensure `scikit-learn`, `matplotlib`, and `pandas` are installed.
3. Run all cells to generate the standardized data, metrics, and side-by-side comparison plots.
