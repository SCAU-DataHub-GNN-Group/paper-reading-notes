# Paper Notes

+ Author:Lai Jun Long.
+ Contact:junlong_lai1@163.com.

## Notes:

- [x] [Spatial-Temporal Fusion Graph Neural Networks for Traffic Flow Forecasting](https://arxiv.org/pdf/2012.09641.pdf), *AAAI 21*

**Tasks** 
+ Traffic prediction.

**Challenges**  

Existing methods can not well take into account the complex situation in traffic flow prediction,i.e., heterogeneity (such as commercial street and residential street, there are still many cases that can be considered) and it is difficult to capture local correlation and global correlation at the same time.

**Drawback of existed methods** 

+ The spatial graph given by the existing methods does not reflect the hidden space-time dependence.
+ Existing methods are difficult to capture both local and global dependencies.

**Solution** 

1. Generate temporal diagrams. Generate time graph based on fast DTW time series similarity.
2. Time graph is introduced into a new temporal fusion graph, and the neural module of temporal fusion graph is obtained.
3. Spatio-temporal fusion graph neural module and gated convolution module are combined. The output of each STFGN module is added to the gated CNN output to become the input of the next STFGN layer.

**Key Reference**

- [Spatial-Temporal Synchronous Graph Convolutional Networks: A New Framework for Spatial-Temporal Network Data Forecasting](https://ojs.aaai.org//index.php/AAAI/article/view/5438), *AAAI 20*. 
# Revelation
 The same data can mine useful information from different angles, and different information can promote each other.

---
NEXT ONE

---
## Notes:

- [x] [Traffic Flow Forecasting with Spatial-Temporal Graph Diffusion Network](https://www.aaai.org/AAAI21Papers/AISI-9334.ZhangX.pdf), *AAAI 21*

**Tasks** 
+ Traffic prediction.

**Challenges**  

+ Temporal dimension: Dependencies between different resolutions.
+ Spatial dimension: Dependence of similar areas.

**Drawback of existed methods** 

+ Most methods only focus on the adjacent spatial correlation between adjacent regions, but ignore the global geographic context information.
+ The existing methods cannot encode the complex traffic change laws with time dependence and multi-resolution.

**Solution** 
1. Time dimension:Feature coding is carried out at different time granularity to obtain the traffic trend in different periods, such as hourly, daily and weekly traffic fluctuation rules. For the traffic sequence modeling under each time granularity, the information fusion module based on self-attention mechanism is used to learn the relationship between traffic data in different time intervals in history.
2. Spatial dimensions:By embedding based on Attention learning in the constructed region graph, the learned region representation vector is potentially integrated with the traffic information of other related regions.
---
NEXT ONE

---
## Notes:

- [x] [Spectral Temporal Graph Neural Network for Multivariate Time-series Forecasting](https://papers.nips.cc/paper/2020/file/cdf6581cb7aca4b7e19ef136c6e601a5-Paper.pdf), *NeurIPS 2020*

**Tasks** 
+ Traffic prediction.

**Challenges**  

+ Multivariable time series prediction often requires simultaneous modeling of the time model within a single variable and the relationship between multiple variables.
+ Most existing models can only capture time patterns in the time domain and require a predefined adjacency matrix.

**Drawback of existed methods** 

+ Most models only capture temporal correlations in the time domain and resort to pre-defined priors as inter-sequence relationships.

**Solution** 
1. Topology of data-driven learning graph.
2. Feed the graph into the StemGNN Layer.
3. The designed loss function is expressed as a combination of predicted loss and backtracking loss.
4. Rolling strategy is used for multi-step prediction.
---
NEXT ONE

---
## Notes:

- [x] [FC-GAGA: Fully Connected Gated Graph Architecture for Spatio-Temporal Traffic Forecasting](https://arxiv.org/pdf/2007.15531.pdf), *AAAI 2021*

**Tasks** 
+ Traffic prediction.

**Challenges**  

+ Model complexity.
+ Graph topology learning mode

**Drawback of existed methods** 

+ The complexity and uptime of existing models is high.
+ Some models rely on predefined relationships between variables.
+ Existing models tend to rely on markov assumptions

**Solution** 
1. Node embedding is used to better represent nodes.So get the Node embedding matrix E.
2. The weight matrix is obtained by node embedding.So get the weight matrix W.
3. Time Gate is integrated with Node embedding for Time modeling.
4. The topology structure G of Graph is generated in Graph Gate module by using weight matrix and input matrix and hard gate mechanism.
5. Then the matrix E, X and G are transposed side by side to obtain the matrix Z, which represents the matrix integrating spatio-temporal information. Just like the previous paper, after learning the time matrix and space matrix and adding a connection matrix, the fusion graph can be obtained according to a certain arrangement.
6. The idea of ResNets is then used so that multiple blocks can be stacked and the results of each Block are added to wait for the predicted value of this layer.
7. Stack multiple layers and average the prediction results of multiple layers to get the final prediction value.
