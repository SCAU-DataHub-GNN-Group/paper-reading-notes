# Paper Notes

- Author: Zhu Fang.
- Contact: zhufang9819@hotmail.com.

## Notes:
- [x] [Traffic Flow Forecasting with Spatial-Temporal Graph Diffusion Network](https://www.aaai.org/AAAI21Papers/AISI-9334.ZhangX.pdf), *AAAI 21*. 

**Tasks**: Traffic prediction.

**Challenges**:

- Multi-resolution case and the factor of geographical contextual information.

**Drawback of existed methods** :

- In the multi-resolution perspective, these methods only consider the short term and smooth dynamics rather than the high dimensional time horizon. In the aspect of geographical contextual information, these methods don't get use of the information at the global level and the relations across the regions.

**Contributions** :

- Solution of multi-resolution: using attention mechanism to construct an multi-temporal level model. 
- Solution of geographical region: using GAT and graph-diffusion mechanism to construct an architecture.
- Aggregate them.

**Datasets**:

​	BJ-Taxi, NYC-Taxi, NYC-Bike-1, NYC-Bike-2.

**Key Reference**

- [DeepCrime: Attentive Hierarchical Recurrent Networks for Crime Prediction](http://urban-computing.com/pdf/CIKM2018deepcrime.pdf), *CIKM 2018*.
- [Diffusion Convolutional Recurrent Neural Network: Data-Driven Traffic Forecasting](https://arxiv.org/pdf/1707.01926v3.pdf), *ICLR 2018*.
- [Revisiting Spatial-Temporal Similarity: A Deep Learning Framework for Traffic Prediction](https://arxiv.org/pdf/1803.01254.pdf), *AAAI 2019*.
- [Graph Attention Networks](https://arxiv.org/pdf/1710.10903v3.pdf), *ICLR 2018*.


---
- [x] [Spatial-Temporal Fusion Graph Neural Networks for Traffic Flow Forecasting](https://arxiv.org/abs/2012.09641), *AAAI 2021*.

**Tasks**: Traffic prediction

**Challenges**

- Information of the given spatial matrix is not sufficient for model learning.

**Drawbacks of existed methods**:

- Ignore the temporal similarity between nodes then modeling the adjacency matrix.
- Ineffective to capture dependencies between local and global correlations.

**Contributions**

- Using fast-DTW algorithm to computer the similarity between two sequences of time-series data w.r.t two different nodes, and construct the temporal matrix $A_{TG}$.
- Aggregate $A_{TG}, A_{TC}, A_{SG}$ to construct the $A_{STFG}$ matrix.
- Construct the STFGN module with GLU function, residual connection-like operation.

- Add the output of STFGN module with Gated CNN module to capture the long-range spatial-temporal dependencies.

**Key Reference**

- [Spatial-temporal synchronous graph convolutional networks: A new framework for spatial-temporal network data forecasting](https://ojs.aaai.org/index.php/AAAI/article/view/5438), *AAAI 2020*.
- [Spatio-Temporal Graph Convolutional Networks: A Deep Learning Framework for Traffic Forecasting](https://www.ijcai.org/proceedings/2018/0505), *IJCAI 2018*.

