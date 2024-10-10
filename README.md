# Optimization-on-Graph-Neural-Network
Author: Prince Kumar
Project Overview
This project explores a hardware-software (HW-SW) co-optimization approach aimed at reducing the inference latency and training time of Graph Neural Networks (GNNs). GNNs, with their large adjacency matrices, pose significant computational challenges during training and inference. This study leverages adjacency matrix re-arrangement and graph partitioning techniques, combined with GPU acceleration, to improve performance with manageable accuracy trade-offs.

Key Contributions:
Software Optimization: Partitioning graphs into smaller sub-graphs and re-arranging adjacency matrices to group highly connected nodes, reducing computational complexity.
Hardware Optimization: Accelerating training and inference using GPU instead of traditional CPU for faster execution.
This project evaluates the proposed optimizations on widely used GNN models, including GCN, GraphSAGE, GIN, and SGC, using popular datasets such as Cora, CiteSeer, and PubMed.

Methodology
The core steps of the project include:

Baseline Establishment:

Train and test GCN, GraphSAGE, GIN, and SGC models on the original datasets.
Record baseline accuracy, training time, and inference latency.
Graph Partitioning:

Partition the graph using the Multi-level Recursive Bisection algorithm from the METIS tool.
Re-arrange the adjacency matrix according to the partitions.
Performance Evaluation:

Analyze the impact on training time, inference latency, and accuracy using the partitioned graphs.
GPU Acceleration:

Run the models on GPU for further optimization.
Record performance gains on GPU compared to CPU.
Datasets
The experiments are conducted on the following citation network datasets:

Cora: 2708 nodes, 10556 edges, 7 classes, 1433 features.
CiteSeer: 3327 nodes, 9104 edges, 6 classes, 3703 features.
PubMed: 19717 nodes, 88648 edges, 3 classes, 500 features.
GNN Models
The following GNN architectures were used:

Graph Convolutional Network (GCN)
Graph Isomorphism Network (GIN)
GraphSAGE
Simple Graph Convolution (SGC)
Results
Baseline Performance
Dataset	Model	  Training Time (ms)	    Inference Latency (ms)	        Test Accuracy
Cora	GCN	       35.72	                     12.67	                        80.3%
Cora	GIN	       115.80	                     78.79	                        71.8%
Cora	GraphSAGE	 102.78	                     71.79	                        79.03%
Cora	SGC	       23.49	                     9.05	                          80%

GPU Performance Gains
Training time and inference latency were significantly improved when using GPU, as shown below:

Model	CPU Training Time (ms)	GPU Training Time (ms)	Training Time Gain (%)
GCN	        21.47	                3.56	               83.40%
GIN	        80.72	                3.34	               95.85%

Conclusion
This project demonstrates that HW-SW co-optimization for GNNs can significantly reduce training time and inference latency with manageable losses in accuracy. Future work will focus on further optimizing partitioning techniques and applying the approach to more real-world applications and hardware accelerators.

Installation
To reproduce the experiments, follow these steps:

git clone https://github.com/your-repository-link
cd your-repository-link
Install required dependencies:

pip install -r requirements.txt
Run the experiments:

References
Kipf, T. N., & Welling, M. (2017). Semi-supervised classification with graph convolutional networks. ICLR.
Hamilton, W., Ying, R., & Leskovec, J. (2017). Inductive representation learning on large graphs. NeurIPS.
