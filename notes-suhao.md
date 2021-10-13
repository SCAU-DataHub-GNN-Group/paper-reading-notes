# Paper Notes

- Author: Su Hao.
- Contact: 1204703687@qq.com.

## Notes:
- [x] [Traffic Flow Forecasting with Spatial-Temporal Graph Diffusion Network](https://www.aaai.org/AAAI21Papers/AISI-9334.ZhangX.pdf), *AAAI 21*. 

**Tasks** Traffic Flow Forecasting.

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
- [Mist: A multiview and multimodal spatial-temporal learning framework for citywide abnormal event forecasting](https://arxiv.org/pdf/2001.04346.pdf)*WWW 2019*
- [Diffusion Convolutional Recurrent Neural Network: Data-Driven Traffic Forecasting](https://arxiv.org/pdf/1707.01926v3.pdf), *ICLR 2018*.
- [Revisiting Spatial-Temporal Similarity: A Deep Learning Framework for Traffic Prediction](https://arxiv.org/pdf/1803.01254.pdf), *AAAI 2019*.
- [Graph Attention Networks](https://arxiv.org/pdf/1710.10903v3.pdf), *ICLR 2018*.

**Question**
- Can the method of adaptive learning adjacency matrix be applied to the model in this paper?

- [ ] [Spatial-Temporal Fusion Graph Neural Networks for Traffic Flow Forecasting](https://arxiv.org/abs/2012.09641), *AAAI 2021*.
