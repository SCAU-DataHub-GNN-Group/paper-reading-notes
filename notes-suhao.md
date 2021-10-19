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

- [x] [DIFFUSION CONVOLUTIONAL RECURRENT NEURAL NETWORK: DATA-DRIVEN TRAFFIC FORECASTING](https://arxiv.org/pdf/1707.01926), *ICLR 2018*.

**Tasks** 
- Traffic Flow Forecasting.

**Challenges**  
- The complex spatial dependence of road network.
- The time dynamics of road condition change and nonlinearity.
- The inherent difficulties of long-term prediction.

**Drawback of existed methods** 
- Simple time series models rely on the stationarity assumption.
- Without considering the spatial structure.
- Some models are only for undirected graphs.

**Proposed model** 
- The author proposes Diffusion Convolutional Recurrent Neural Network (DCRNN) that integrates diffusion convolution,the sequence to sequence architecture and the scheduled sampling technique.
- This paper presents DCRNN, which uses diffusion convolution, sequence to sequence learning framework and predetermined sampling to capture space and time dependence.

**Contributions**
- In this paper, the spatial correlation of traffic is modeled as a diffusion process on a directed graph, and a diffusion convolution is proposed, which can be calculated effectively.
- The model supports data-driven construction of dependency graphs of different time series.

**Solution** 
- Solution of spatial dependency modeling:In this paper, diffusion convolution is defined, in which the diffusion form is characterized by random walks on a graph. Finally, this Markov process converges to a stationary distribution.
- Solution of time dynamic modeling:In this paper,GRU is used and the matrix multiplication in GRU is replaced by diffusion convolution. In the multi-step prediction, the sequence to sequence architecture is adopted, in which the encoder and decoder are recurrent neural network with DCGRU.

**Key Reference**
- [Diffusion-convolutional neural networks](https://arxiv.org/pdf/1511.02136.pdf),*NIP 2016*
- [Convolutional sequence to sequence learning](https://arxiv.org/pdf/1705.03122.pdf),*ICML 2017*

- [x] [Graph Wavelet Neural Network](https://arxiv.org/pdf/1904.07785.pdf), *ICLR 2019*.

**Tasks** 
- Graph feature extraction.

**Challenges**  
- The non-Euclidean nature of graph is the main obstacle or challenge.

**Drawback of existed methods** 
- It is difficult to determine a suitable neighborhood by spatial method.
- The modeling of spectral method must be based on the eigenvalue decomposition of graph Laplace matrix, which has high complexity.
- The Fourier base vector in spectral method is dense, which can not be accelerated by sparse matrix in large-scale graph operation, which reduces the efficiency of the model.
- The Fourier vector in the spectral method is not enough to highlight the localization feature.

**Proposed model** 
- This paper proposes a graph wavelet neural network (GWNN) based on graph wavelet transform.

**Contributions**
- The wavelet basis vector is used to replace the Fourier basis in the original spectral method, which is sparse, efficient and clear.
- An innovative graph wavelet neural network (GWNN) is proposed and an efficient algorithm is designed to decouple feature extraction and graph convolution to improve operation efficiency.

**Solution** 
- Solution of limitations of Fourier basis of graph structure:using wavelet basis to replace Fourier basis in graph convolution.
- Solution of lots of parameters of the model:The graph convolution based on wavelet basis is decoupled into feature transformation and graph convolution.

**Key Reference**
- [Spectral networks and locally connected networks on graphs](https://arxiv.org/pdf/1312.6203.pdf),*ICLR 2014*
- [ Graph wavelets for multiscale community mining](http://perso.ens-lyon.fr/pierre.borgnat/Papiers/14_Tremblay_ieeeTSP_06870496.pdf),*IEEE  2014*

- [x] [Spatio-Temporal Graph Convolutional Networks: A Deep Learning Framework for Traffic Forecasting](https://www.ijcai.org/proceedings/2018/0505.pdf), *IJCAI 2018*.

**Tasks** 
- Traffic Forecasting.

**Challenges**  
- Strong nonlinearity and complexity of traffic flow.

**Drawback of existed methods** 
- It is difficult to extract spatial and temporal features from input.
- Convolution operation limits the model to deal with conventional grid structures.
- The learning of sequence by cyclic neural network will lead to the accumulation of error.

**Proposed model** 
- A spatiotemporal graph convolution network (STGCN) is proposed, in which a generalized graph is used to model the traffic network, and a full convolution structure is deployed on the time axis to prevent the cumulative effect.

**Contributions**
- Pure convolution is applied to extract spatiotemporal information from time series of graph structure at the same time.
- The training speed is more than 10 times faster and requires fewer parameters.

**Solution** 
- Solution of extracting spatial features:using graph convolution formula after Chebyshev approximation and first-order approximation.Consider not only the state of neighbor nodes, but also their own state.
- Solution of extracting temporal features:using gated convolution to capture time dependence and GLU operation which may alleviate the phenomenon of gradient disappearance and retain the nonlinear ability of the model.

**Key Reference**
- [Semi-supervised classification with graph convolutional networks](https://arxiv.org/pdf/1609.02907v2.pdf),*ICLR 2016*

- [x] [Neural Ordinary Differential Equations](https://arxiv.org/pdf/1806.07366.pdf), *NIPS 2018*.

**Tasks** 
- A new family of deep neural network models.

**Challenges**  
- Applying neural networks to irregularly-sampled data.

**Drawback of existed methods** 
- They assume that the sample is evenly sampled from the population, but this is often not the case in reality.
- They assume that the interval between these observations and potential variables is fixed, which often leads to the deviation of the estimated distribution from the overall distribution.

**Proposed model** 
- The author uses Neural ODE which can model the time series as a continuously changing trajectory.

**Contributions**
- The author takes the derivative of the hidden state as a parameter without consuming a lot of space to store the intermediate results.
- By explicitly changing the accuracy of numerical integration, the speed and accuracy of the model can be adjusted freely.

**Solution** 
- Solution of Irregular sampling and random latent variables:The author uses latent ODE model to model time series, in which potential trajectories are used to represent each time series. Each trajectory is determined by the local initial state and a set of global potential dynamics shared in all time series.


**Key Reference**
- [Auto-encoding variational Bayes](https://arxiv.org/pdf/1312.6114.pdf),*ICLR 2014*

- [x] [GMAN: A Graph Multi-Attention Network for Traffic Prediction](https://arxiv.org/pdf/1911.08415.pdf), * AAAI 2020*.

**Tasks** 
- Traffic Prediction.

**Challenges**  
- The complexity of traffic systems and the constantly changing nature of many impacting factors.

**Drawback of existed methods** 
- Dynamic spatial correlation and nonlinear temporal correlation can not be well captured.
- In long-term forecasting, small errors in each time step may be amplified.

**Proposed model** 
- The author proposes a graph multi-attention network (GMAN).It adapts an encoder-decoder architecture, where both the encoder and the decoder consist of multiple spatio-temporal attention blocks to model the impact of the spatio-temporal factors on traffic conditions.

**Contributions**
- Spatial and temporal attention mechanisms are proposed to simulate the dynamic spatial and nonlinear temporal correlation.
- A gating fusion algorithm is designed to adaptively fuse the information extracted by spatial and temporal attention mechanisms.
- Propose a transformational attention mechanism to transform historical traffic characteristics into future manifestations.

**Solution** 
- Solution of  the evolution of traffic conditions restricted by theunderlying road network:using the node2vec method to learn the vertex representation and sending these vectors into a two-layer fully connected neural network.
- Solution of representing the dynamic correlation between nodes:apply a two-layer fully-connected neural network to transform the time feature to a vector.
- Solution of capture the correlation in high dynamics of roads:A spatial attention mechanism is designed to adaptively capture the correlation between sensors in road network. The key idea is to dynamically assign different weights to different vertices in different time steps.
- Solution of nonlinear time correlation:The hidden state is connected with spatiotemporal embedding, and the multi-head method is used to calculate the attention score.
- Solution of alleviate the error propagation effect between different prediction time steps for a long time:The transformation attention layer is added to model the direct relationship between each future time step and each historical time step, so as to transform the encoded traffic characteristics and generate the future representation as the input of the decoder.
 
**Key Reference**
- [Node2vec: scalable feature learning for networks](https://www.kdd.org/kdd2016/papers/files/rfp0218-groverA.pdf),*KDD 2016*
