# Visualization and Case Study

**Q3**: Although the article theoretically demonstrates the usefulness of the proposed method, some of the assumptions may be difficult to satisfy when training the model from my perspective. Therefore, it is possible to learn the complete common information but there is no guarantee that the learned common information is totally clean. And thus the paper lacks a case study of the learned common representation and private representation.

**A3**: In the following, we design two case studies to verify other comments from this question.

**Case Study 1 verifies the statement “the common information learned by our method is clean”** by calculating the correlation between the common representations and the private representations, i.e., the smaller the correlation between the common representation and the private representation, the cleaner the common information learned by the representation learning method. To do this, we implemented our method on the ACM dataset, and visualized the correlation of learned representations (concatenated by common and private representations, dimension of them are both set as 8) in Figure 1. More specifically, the correlation map includes four blocks, where both the upper right block and the lower left block indicate the correlation between the common representation and the private representation. Based on Figure 1, their correlations are small, so the common information learned by our method is clean. 

**Case Study 2 verifies the statement "the common part and the private part of our method do learn common and private knowledge"**. Specifically, given the dataset ACM with two views, i.e., PSP and PAP, we randomly generate a toy dataset with 14 nodes. In the toy dataset, the edges appeared in two views (e.g., the edge between node 4 and node 5 (Edge_4-5 for short), and Edge_1-8) belong to the common part, while the edges appeared in only one view (e.g., Edge_1-11) belong to the private part. Note that, an edge connecting two nodes indicates that these two nodes are with high correlation in the correlation map. The edges belonging to the common part indicate that these two nodes are with high correlation in all views, while the edges belonging to the private part indicate that these two nodes are with high correlation in only a part of views. We conduct our method on the ACM dataset and visualize the correlation map of all node pairs (i.e., the correlation of any two nodes) of the toy dataset in Figure 2. Obviously, our method can learn the common knowledge, e.g., node 4 and node 5 connected by Edge_4-5 have a high correlation in both the PSP view and the PAP view, while node 1 and node 11 connected by Edge_1-11 have a high correlation in the PAP view and low correlation in the PSP view. This visualization verifies that the common part learns the common knowledge and the private part learns the private knowledge in real-world datasets.
<p align="center">
<img src=https://github.com/mujin2020/Casestudy2/blob/main/Case-Study/Figures/Correlation_new.png
 width=50% />
 </p >
 <p align="center">
 <span><b> 
 Figure1. The correlation map of common and private representations learned by the proposed DMG on the ACM dataset.
 </b></span>
 </p >



<p align="left">
<img src=https://github.com/mujin2020/Casestudy2/blob/main/Case-Study/Figures/example_graph0.png
 width=100% />
 <img src=https://github.com/mujin2020/Casestudy2/blob/main/Case-Study/Figures/example_graph1.png
 width=100% />
 <span><b>Figure2. Toy dataset and corresponding node correlation maps of the learned common and private representations. The toy dataset is randomly sampled with the same nodes set from PSP and PAP graphs of the ACM dataset, respectively, and different colors indicate different node labels.</b></span>
 </p >

