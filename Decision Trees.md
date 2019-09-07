# Decision Trees

***
### Overview
* What is a Decision Tree
* Feature Selection
	* Good vs Bad features
	* Information Theory - Entropy
* How to build a Descision Tree?
	* ID3 top-down algorithm
	* Information Gain

***


* A classification model to predict class labels by learning decision rules inferred from training data.
 <center><img src="./static/blogs-images/Decision-tree.png" width="400"></img></center>

* **Basic Idea:** Build a tree model that splits the training set into subsets in which all examples have the same class.
	* Splitting is done using rules inferred from the training set.
	* Each rule is based on a feature, and the split corresponds to the values it can take
	* If necessary, each subset can be split again using another feature, and so on until all examples have the same class.
	* Once the tree is built, we can use it to quickly classify new input examples - this is an eager learning strategy.

* Process
	1. Initially all examples in the training set are placed at the root node of the tree.
	<center><img src="./static/blogs-images/decision-tree-root-node.png" width="300"></img></center>
	
	2. One of the available features (A) is now used to split the examples at the root node into two or more **child nodes** containing subsets of examples.
	<center><img src="./static/blogs-images/decision-tree-child-node.png" width="300"></img></center>
	
	3. The same process is now applied to each child node, except for any child node at which all examples have the same class.
	<center><img src="./static/blogs-images/decision-tree-growing.png" width="300"></img></center>
	4. This continues until the training set has been divided into subsets in which all the examples have the same class.
	<center><img src="./static/blogs-images/decision-tree-full.png" width="400"></img></center>
	
* Node Purity
	* A tree node is **pure** if all examples at that node have the same class label.
	<center><img src="./static/blogs-images/node-purity.png" width="400"></img></center>
	
	* A decision tree in which all the leaf nodes are pure can always be constructed provided there are **no clashes** in the data.
	
	* Most decision tree algorithms use some measure of node (im)purity to choose features to split when building the tree. This measure guides the learning process.

* Objective
	* A **“good”** decision tree will classify all examples correctly using as few tree nodes as possible.
	
	* Objective in building a decision tree is to choose good features so as to minimise the depth of the tree.

	
* Good vs Bad Features
	* **Good Features:** A perfect feature divides examples into categories of one class ⇒ high purity
	<center><img src="./static/blogs-images/good-features.png" width="300"></img></center>

	* **Bad Features:** A poor choice of feature produces categories of mixed classes ⇒ high impurity

	<center><img src="./static/blogs-images/bad-features.png" width="300"></img></center>
	
* Feature Selection
	* **Goal:** Find good features which divide examples into categories of a single class
	
	*  Feature selection algorithms have been developed which use impurity as an objective to guide feature selection   (e.g. Entropy, Gini impurity).
 
	* **Common selection strategy in decision trees:**
		* For each feature, some measure of impurity is applied to the current set of tree nodes.
		* The feature that maximises **the reduction in impurity** is
selected as the next most useful feature.

* Entropy
	* **Entropy:** In information theory, a measure of uncertainty around a source of information. Low for predictable sources, higher for more random sources.

	* In the context of decision trees, entropy provides a measure of impurity - how uncertain we are about the decision for a given set of examples.
	
	 <center><img src="./static/blogs-images/entropy.png" width="250"></img></center>
	 
	* **Definition:** 
	 	* Entropy of a set of examples ***S*** with class labels {C1,...,Cn} :
	 	<center><img src="./static/blogs-images/entropy-2.png" width="200"></img></center>
	 	* where pi is the relative frequency (probability) of class Ci.
	* Examples:
		* The lowest possible entropy (i.e. zero) occurs when all examples have the same class label.
		* The highest entropy occurs when we are most uncertain.
		<center><img src="./static/blogs-images/entropy-examples.png" width="500"></img></center>

* Top-Down Induction of Descision Trees
	* **ID3 Algorithm:** Popular algorithm which repeatedly builds a decision tree from the top down (Quinlan, 1986).
	* Start with an empty tree and set of all training examples S.

			ID3( S ):
				• IF all examples in S belong to the same class C THEN
					– Return new leaf node and label it with class C. 
				• ELSE
					– Select a feature A based on some
					– Generate a new tree node with A as the test feature. 
					– FOR EACH value vi of A:
						* Let Si ⇢ S contain all examples with A = vi. 
						* Build subtree by applying ID3( Si )
	

* Criterion: Information Gain
	* **Information Gain (IG):** Popular information theoretic approach for selecting features in decision trees, based on entropy.
	* Measures a feature’s overall impact on entropy when used to split a set of training examples into two or more subsets.
		* How much information do we learn by splitting on the feature?
		* How much is the reduction in entropy?
	* **Definition:**
		* IG for feature ***A*** that splits a set of examples ***S*** into {*S1,...,Sm*} :
	<center><img src="./static/blogs-images/information-gain.png" width="400"></img></center> 
	* Example:
		* Initial training set has 6 Yes, 6 No examples.
		* Which feature should we select to split at the root node?
		<center><img src="./static/blogs-images/information-gain-example.png" width="600"></img></center>
		* Feature “Patrons” has higher IG, so a better choice for splitting.
		
* Handling Inconsistent Data
	* Inconsistent training data occurs when two identical examples from the training set have different labels:
	<center><img src="./static/blogs-images/inconsistent-data.png" width="400"></img></center>
	* When building a tree, this can result in cases where **leaf nodes are not “pure”** and **no features are left to split**.
	
	* Simple solution:
		* For the label, take the majority vote at the leaf node.
		* If there is a tie, randomly choose one of the class labels.
		<center><img src="./static/blogs-images/inconsistent-data-2.png" width="150"></img></center>