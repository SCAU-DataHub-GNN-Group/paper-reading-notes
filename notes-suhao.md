# Paper Notes

- Author: Su Hao.
- Contact: 1204703687@qq.com.

## Notes:
- [x] [Traffic Flow Forecasting with Spatial-Temporal Graph Diffusion Network](https://www.aaai.org/AAAI21Papers/AISI-9334.ZhangX.pdf), *AAAI 21*. 

**Tasks** 
- Traffic Flow Forecasting.

**Challenges**  
- The graph spatial information includes not only the adjacency of local space, but also the global geographical background (cross regional dependency)
- More complex multi-resolution dependencies (hours, days, weeks)

**Drawback of existed methods** 
- They are only effective for short-term and smooth dynamics, and they are difficult to predict in high-order multi-dimensional time range.
- They only focus on the geographical correlation nearby, while ignoring the cross regional interdependence in the global context.

**Proposed model** 
- The author proposed a hierarchical graph neural network model with multi-scale self attention network and attention graph diffusion paradigm.

**Solution** 
- Solution of multi-resolution: using a multi-scale self-attention network to encode dynamic granularity with different time resolutions and add an aggregation layer.
- Solution of geographical region: using a hierarchical graph neural network combining graph attention network and graph convolution based diffusion mechanism.

**Key Reference**
- [Stepdeep: a novel spatial-temporal mobility event prediction framework based on deep neural network](https://dl.acm.org/doi/pdf/10.1145/3219819.3219931),*KDD 2018*
- [Region Representation Learning via Mobility Flow](https://dl.acm.org/doi/pdf/10.1145/3132847.3133006),*CIKM’17*
- [Mist: A multiview and multi-modal spatial-temporal learning framework for citywide abnormal event forecasting](https://arxiv.org/pdf/2001.04346.pdf)*WWW 2019*
- [Diffusion Convolutional Recurrent Neural Network: Data-Driven Traffic Forecasting](https://arxiv.org/pdf/1707.01926v3.pdf), *ICLR 2018*.
- [Revisiting Spatial-Temporal Similarity: A Deep Learning Framework for Traffic Prediction](https://arxiv.org/pdf/1803.01254.pdf), *AAAI 2019*.
- [Graph Attention Networks](https://arxiv.org/pdf/1710.10903v3.pdf), *ICLR 2018*.

**Question**
- Can the method of adaptive learning adjacency matrix be applied to the model in this paper?

- [x] [Spatial-Temporal Fusion Graph Neural Networks for Traffic Flow Forecasting](https://arxiv.org/abs/2012.09641), *AAAI 2021*.

**Tasks** 
- Traffic Flow Forecasting.

**Challenges**  
- Complex spatio-temporal correlation between different roads.
- The correlation representation of incomplete adjacent connections of graphs may limit the spatio-temporal dependent learning of these models.

**Drawback of existed methods** 
- Lack of an informative graph construction.
- The modeling of adjacency matrix ignores the time correlation of nodes
- Overfitting of spatial-temporal dependencies learning.
.
**Proposed model** 
- Based on dynamic time warping, the author proposes an s'j algorithm including time fusion graph module and gated expansion convolution.

**Solution** 
- Solution of informative graph construction: Based on DTW,generate Spatial Graph, Temporal Graph and Temporal Connectivity graph and combine them to form Spatial-Temporal Fusion Graph.
- Solution of capturing local and global dependencies: using a Gated dilated CNN module with spatial-temporal fusion graph module in parallel.

**Key Reference**
- [Using dynamic time warping to find patterns in time series](https://www.aaai.org/Papers/Workshops/1994/WS-94-03/WS94-03-031.pdf),*KDD 1994*
- [Deep residual learning for image recognition](https://arxiv.org/pdf/1512.03385.pdf),*IEEE 2016*
- [Spatial-Temporal Synchronous Graph Convolutional Networks: A New Framework for Spatial-Temporal Network Data Forecasting](https://ojs.aaai.org/index.php/AAAI/article/view/5438/5294)*AAAI 2020*
