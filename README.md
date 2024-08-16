## Image Clustering Project

### Introduction
In this project, we aim to perform image clustering using a set of images stored in a directory. The primary goal is to group similar images together by leveraging unsupervised learning techniques. To achieve this, we use the MobileNet model for feature extraction, apply KMeans clustering for grouping the images, and visualize the clustering results. This project demonstrates the complete process, including loading images, extracting features, clustering, and visualizing the results.

### Loading Images
We start by defining a function that loads and preprocesses images from a specified folder. The images are resized to a consistent size (64x64) and stored in a list along with their filenames. This allows us to have a uniform input size for the feature extraction process.

### Feature Extraction using MobileNet
For feature extraction, we utilize the MobileNet model, a lightweight convolutional neural network pre-trained on the ImageNet dataset. We modify the MobileNet architecture by removing the top layers to focus on feature extraction rather than classification. The images are preprocessed, and features are extracted using the MobileNet model. These features are then flattened into a 1D array for further processing.

### Feature Extraction in Parallel
To enhance the efficiency of the feature extraction process, we implement a parallel feature extraction method using the `joblib` library. This allows us to extract features from multiple images simultaneously, significantly reducing the overall processing time.

### Clustering with KMeans
Once the features are extracted, we use the KMeans algorithm to cluster the images based on their extracted features. KMeans is an unsupervised learning algorithm that partitions the data into a specified number of clusters. Each image is assigned a label corresponding to the cluster it belongs to.

### Organizing and Saving Clusters
After clustering, the images are organized into directories based on their cluster labels. The cluster assignments are saved to a file for future reference. We also save the extracted features to a file, allowing us to reload them without having to recompute them in subsequent analyses.

### Visualization of Clusters
To visualize the clustering results, we plot a subset of images from each cluster using `matplotlib`. Additionally, we employ Principal Component Analysis (PCA) to reduce the dimensionality of the feature space for visualization purposes. We generate both 2D and 3D plots to visualize the clusters in a reduced feature space.

### Evaluation of Clustering
The clustering quality is evaluated using the silhouette score, which measures how similar an image is to its own cluster compared to other clusters. A higher silhouette score indicates better-defined clusters.

### Saving Clustered Images
Finally, we save the clustered images into separate folders corresponding to their cluster labels. This step allows us to easily access and review the images in each cluster.

### Conclusion
This project successfully demonstrates the end-to-end process of image clustering using MobileNet for feature extraction and KMeans for clustering. The combination of parallel processing, dimensionality reduction, and cluster visualization provides a comprehensive approach to organizing and understanding large image datasets.
