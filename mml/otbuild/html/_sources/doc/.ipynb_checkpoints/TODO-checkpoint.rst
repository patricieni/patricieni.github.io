TODO List 
============================================
1. Remember to check why the OT matrix $X^*$ is not symmetric

2. In tex, slightly adapt the notation of Cuturi Alg1 so that gradient is not confused with G (the Wasserstein distance)

3. IF the pseudometric matrix has off-diagonal zeros then add some small constant to the whole metric. 

4. Two ways I make this work, I either change the POT implementation to be faster, which is highly unlikely or I train it on smaller datasets, hence less OT to calculate.

5. Optimize the algorithms to return exactly what's needed. 

6. Add the rest of the methods in the mml and add classes instead of pure methods 
7. Check how you'll incorporate nldr in here :) 

8. Can I add extra layers dinamically by parsing args or another smart method? 
 
Some info about visual words, or SIFT (Scale-invariant feature transformations) - these could be used for the algorithm. 

Visual words are based on [Scale-invariant feature transforms (SIFT)](https://en.wikipedia.org/wiki/Scale-invariant_feature_transform). SIFT features are essentially local orientation histograms and capture the properties of small image regions. They possess attractive invariance properties which make them well suited for our task (you can read more about SIFT features in [D.Lowe, IJCV 60(2):91- 110, 2004](http://link.springer.com/article/10.1023/B:VISI.0000029664.99615.94), but the details don't matter for the purpose of this assignment). Each SIFT feature is a 128 dimensional vector. From each image many SIFT features are extracted, typically > 2500 per image (features are extracted at regular intervals using a 15 pixel grid and at 4 different scales). To obtain visual words a representative subset of all extracted SIFT features from all images is chosen and clustered with k-means using 500 centres (such use of the k-means algorithm will be discussed in detail during the lecture). These 500 cluster centres form our visual words. The representation of a single image is obtained by first assigning each SIFT feature extracted from the image to the appropriate cluster (i.e. we determine the visual word corresponding to each feature by picking the closest cluster centre). We then count the number of features from that image assigned to each cluster (i.e. we determine how often each visual word is present in the image). This results in a 500 dimensional count vector for each image (one dimension for each visual word). The normalized version of this count vector gives the final representation of the image (normalized means that we divide the count vector by the total number of visual words in the image, i.e. the normalized counts sum to 1 for each image)