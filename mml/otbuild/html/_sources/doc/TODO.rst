TODO List 
============================================
Double check with Ilias that algorithm is correct. Unit Tests not enough

1. Remember to check why the OT matrix $X^*$ is not symmetric

2. Double check that pre-processing steps are done correctly

3. If the pseudometric matrix has off-diagonal zeros then add some small constant to the whole metric. 

4. Scalability: Sinkhorn or Wasserstein on GPU

5. Optimize Wasserstein to run on arrays

6. Add as much as possible in a PyTorch pipeline

7. Train and *hyper-tune* Caltech and MNIST with PyTorch 

8. Would be nice - a dynamic Autoencoder, changing the arhitecture on the fly

Some info about visual words, or [Scale-invariant feature transforms (SIFT)](https://en.wikipedia.org/wiki/Scale-invariant_feature_transform)
This is the "original" space for MNIST
