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

**Solutions**

- Using fast-DTW algorithm to computer the similarity between two sequences of time-series data w.r.t two different nodes, and construct the temporal matrix $A_{TG}$.
- Aggregate $A_{TG}, A_{TC}, A_{SG}$ to construct the $A_{STFG}$ matrix.
- Construct the STFGN module with GLU function, residual connection-like operation.

- Add the output of STFGN module with Gated CNN module to capture the long-range spatial-temporal dependencies.

**Contributions**
- Applying the DTW algorithm to compute the similarity of different time series so that it can extract the global information. :)

**Key Reference**

- [Spatial-temporal synchronous graph convolutional networks: A new framework for spatial-temporal network data forecasting](https://ojs.aaai.org/index.php/AAAI/article/view/5438), *AAAI 2020*.
- [Spatio-Temporal Graph Convolutional Networks: A Deep Learning Framework for Traffic Forecasting](https://www.ijcai.org/proceedings/2018/0505), *IJCAI 2018*.

---
- [x] [Spectral Temporal Graph Neural Network for Multivariate Time-series Forecasting](https://papers.nips.cc/paper/2020/file/cdf6581cb7aca4b7e19ef136c6e601a5-Paper.pdf), *NeurIPS 2020*.

**Tasks**: Multi-variate timeseries forecasting

**Challenges**
- Need to consider both intra-time series temporal correlations and inter-time series correlation simultaneously.

**Drawbacks of existing methods**
- Ignore the inter-series correlations
- Require a dependency as priors.

**Solutions**
- If the prior matrix is missed, we can construct this matrix by using self-attentnion on the timeseries.
- Using GFT to extract the inter-time series correlations.
- Merging the two operations and construct an residual StemGNN block.
- Using a sequence of DFT operations to extract the intra-time series correlations.
- Add the backcast block to make the representative power more enhanced.
- Based on the backcast block, the author proposed a loss function which measures the forecast error and backcast error simultaneously.
  
**Contributions**
- Using self-attention mechanism to construct the adjacent matrix.
- Using backcast prediction results to enhance the representation.
---
- [x] [FC-GAGA: Fully Connected Gated Graph Architecture for Spatio-Temporal Traffic Forecasting](https://ojs.aaai.org/index.php/AAAI/article/view/17114/16921), *AAAI 2021*.

**Tasks**: Multi-variate timeseries forecasting

**Challenges**
- The complexity and runtime of existed models are very higher.
- Some models rely on the definition of relationships between variables provided by a domain expert.
- Existing models tend to rely on Markovian assumptions to make modelling the interactions across varables.

**Solutions**
- Compute graph edge weights and use them in any place where node's mutual information is needed.
- Use time gate to remove the seasonality from the input of the block and applying it again at the output of the block.
- Use the graph gate to computer the relation between the node i and the every kth timestep's value of node j, then fomulates an N by Nw matrix. Note that the weight value W(i, j) affects the probability of opening the gate. The complexity is O(n^2), which is more effective than existed models with O(n^3) complexity.
- Using an full connected time-series block for prediction.

**Contributions**
- Only use the full connected netword and residual operation to get a good performance.
- The FC-GAGA can stacked and the performance can be imporved by stacked proper layers.
- The complexity of the model is much lower than existing models.

**Key Reference**
- [Gated Graph Sequence Neural Networks](https://arxiv.org/pdf/1511.05493v4.pdf), *ICLR 2016*
- [N-BEATS: Neural basis expansion analysis for interpretable time series forecasting](https://arxiv.org/pdf/1905.10437v4.pdf), *ICLR 2020*.

---
- [x] [Diffusion Convolutional Recurrent Neural Network: Data-Driven Traffic Forecasting](https://arxiv.org/pdf/1707.01926), *ICLR 2018*.

**Tasks**: Traffic forecasting.

**Challenges**
- Complex spatiotemporal dependencies and inherent diffculty in the long term forecasting.

**Solutions**
- Diffusion convolution(DC) captures the spatial dependency, which utilizes an approximation of the stationary distribution(Markov transmit distribution).
- Combine the DC with traditional GRU module and construt the DCGRU module.
- Use the DCGRU module to implement an seq2seq model for forecasting.

**Contributions**
- Much lower complexity than the traditional spectral-based graph convolution, O(K|E|) << O(N^2).
- Giving a proof that the spectural graph convolution is specific condition of the diffution convolution.
- Using ablation study to conclude that directed graph is better than undirected one in capturing the asymmetric correlation.






