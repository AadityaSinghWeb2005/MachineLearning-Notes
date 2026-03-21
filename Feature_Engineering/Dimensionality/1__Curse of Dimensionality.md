

In dataset You called features as Dimensions 
The idea is there should be a Optimal No. of features should be present in the Model 
It will increase Your performance and accuracy 
When the No. of features become increase and more than Optimal No. of features then 
It can have worse effects on Your Model it can also decrease Your accuracy 
**Eg.** In a mnist dataset we use 728 pixels mean 728 Features But when You look into it YOu find that only pixel related which Represent Number are relevant to us Not most of the Pixels So we dont need those pixels or features which just occupying extra space or just increasing the computation without adding any benefit 

Curse of Dimensionality mainly occurs in high dimensional Data : Text , Images 

**What is the problem in Higher dimensional Dataset ?** 
The reason is sparsity(means dataset so much far from each other in Big space )  in higher dimensional.
Because of this Your Machine Learning Algorithms  Like KNN Failed ( because it calculates the Closest Distance but due to data is sparse it Makes no Point )
Due to this performance decreases 
Computation Increases
**Solution** : Dimensionality Reduction : two ways to do it -> Feature selection OR Feature Extraction 

**Feature Extraction** : we create a new set of columns from the given columns 
There are three Techniques Used in this 
	1. PCA (principle Component analysis)
	2. LDA (linear Discremininant Analysis )
	3. tsne 