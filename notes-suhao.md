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

**Proposed model** 
- Based on dynamic time warping, the author proposes an s'j algorithm including time fusion graph module and gated expansion convolution.

**Solution** 
- Solution of informative graph construction: Based on DTW,generate Spatial Graph, Temporal Graph and Temporal Connectivity graph and combine them to form Spatial-Temporal Fusion Graph.
- Solution of capturing local and global dependencies: using a Gated dilated CNN module with spatial-temporal fusion graph module in parallel.

**Key Reference**
- [Using dynamic time warping to find patterns in time series](https://www.aaai.org/Papers/Workshops/1994/WS-94-03/WS94-03-031.pdf),*KDD 1994*
- [Deep residual learning for image recognition](https://arxiv.org/pdf/1512.03385.pdf),*IEEE 2016*
- [Spatial-Temporal Synchronous Graph Convolutional Networks: A New Framework for Spatial-Temporal Network Data Forecasting](https://ojs.aaai.org/index.php/AAAI/article/view/5438/5294)*AAAI 2020*

- [x] [FC-GAGA: Fully Connected Gated Graph Architecture for Spatio-Temporal Traffic Forecasting](https://arxiv.org/pdf/2007.15531.pdf), *AAAI 2021*.

**Tasks** 
- Traffic Flow Forecasting.

**Challenges**  
- If the graph structure time series is not modeled, it is difficult for the model to mine and predict the correlation between entities.

**Drawback of existed methods** 
- The complexity and runtime of existed models are significantly higher.
- Some models rely on the definition of the relationship between variables provided by domain experts
- Existing models often rely on Markov assumptions.

**Proposed model** 
- FC-GAGA, that is based on a combination of a fully-connected times series model N-BEATS and a hard graph gate mechanism.

**Contributions**
- The author combines the most advanced univariate TS prediction model N-BEATS with learnable time gate and learnable hard graph gate mechanism.
- The model can effectively learn graph parameters from data and achieve good prediction performance. 
- The model proposed by the author has computational advantages. Compared with the model with similar accuracy, the training time is reduced by at least three times.

**Solution** 
- Solution of modelling time related features: using a multiplicative gate model that divides/multiplies the input/output of the FC-GAGA layer by time effects derived from the time feature and via a fully connected network.
Then,the input time feature vector is concatenated with the node embedding to account for the fact that each node may have a different seasonality pattern.Finally, the input and output time effects are allowed to be decoupled through a separate linear projection layer.
- Solution of nodes correlation: using a graph gate block which based on hard gating to capture the correlation of nodes in each layer by learning the weight matrix.
- Solution of limitation of Markov model based on node proximity:Using FC-GAGA stacking, each layer of the model can freely set gates for cross node information flow according to the processing completed by the previous layer. Finally, the final output of the model is equal to the average value of layer prediction.

**Key Reference**
- [N-BEATS: Neural basis expansion analysis for interpretable time series forecasting](https://arxiv.org/pdf/1905.10437v4.pdf),*ICLR 2020*
- [Spatial-Temporal Synchronous Graph Convolutional Networks: A New Framework for Spatial-Temporal Network Data Forecasting](https://ojs.aaai.org/index.php/AAAI/article/view/5438/5294),*AAAI 2020*

- [x] [Spectral Temporal Graph Neural Network for Multivariate Time-series Forecasting](https://papers.nips.cc/paper/2020/file/cdf6581cb7aca4b7e19ef136c6e601a5-Paper.pdf), *NeurIPS 2020*.

**Tasks** 
- Multivariate Time-series Forecasting.

**Challenges**  
- Multivariate time series prediction needs to consider both the time correlation within the series and the correlation between the series.

**Drawback of existed methods** 
- Only capture the temporal patterns in the time domain.
- Need a predefined relationship topology between sequences.

**Proposed model** 
- The author proposes Spectral Temporal Graph Neural Network (StemGNN) which combines Graph Fourier Transform (GFT) to model inter-series
correlations and Discrete Fourier Transform (DFT) to model temporal dependencies in an end-to-end framework.

**Contributions**
- StemGNN is the first work to represent both intra sequence and inter sequence correlations in the spectral domain.
- The model supports data-driven construction of dependency graphs of different time series.

**Solution** 
- Solution of without predefined topology relationships:Input to the potential correlation layer which combines a GRU layer and self-attention mechanism and automatically infer the structure of the graph and its related weight matrix W from the data.
- Solution of modelling structural and temporal dependencies inside multivariate time-series jointly in the spectral domain:
Pass g = (x, w) into the StemGNN block.First, the graph Fourier transform (GFT) operator transforms graph G into a spectral matrix representation, in which the univariate time series of each node becomes linearly independent. 
Then, the discrete Fourier transform (DFT) operator transforms each univariate time series component to the frequency domain. In the frequency domain, the representation is fed into 1D convolution and Glu sublayer to capture the characteristic mode, 
and then converted back to the time domain by inverse DFT(IDFT). Finally,apply graph convolution to spectral matrix representation and inverse GFT(IGFT).

**Key Reference**
- [N-BEATS: Neural basis expansion analysis for interpretable time series forecasting](https://arxiv.org/pdf/1905.10437v4.pdf),*ICLR 2020*
- [Time-series anomaly detection service at microsoft](https://arxiv.org/pdf/1906.03821.pdf)*KDD 2019*
