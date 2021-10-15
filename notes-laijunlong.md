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
