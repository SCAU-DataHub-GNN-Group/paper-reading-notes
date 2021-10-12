# Paper Notes

- Author: Zhu Fang.
- Contact: zhufang9819@hotmail.com.

## Notes:
- [x] [Traffic Flow Forecasting with Spatial-Temporal Graph Diffusion Network](https://www.aaai.org/AAAI21Papers/AISI-9334.ZhangX.pdf), *AAAI 21*. 

**Tasks** Traffic prediction.

**Challenges**  
- Multi-resolution case and the factor of geographical contextual information.

**Drawback of existed methods** 
- In the mutli-resolution perspective, these methods only conider the short term and smooth dynamics rather than the high dimensional time horizon. In the aspect of geophaphical contextual information, these methods don't ge use of the information at the global level and the realations across the regions.

**Solution** 
- Solution of multi-resolution: using attention mechanism to construct an multi-temporal level model. 
- Solution of geographical region: using GAT and graph-diffusion mechanism to construct an architecture.
- Aggregate them.

**Key Reference**
- [DeepCrime: Attentive Hierarchical Recurrent Networks for Crime Prediction](http://urban-computing.com/pdf/CIKM2018deepcrime.pdf), *CIKM 2018*.
- [Diffusion Convolutional Recurrent Neural Network: Data-Driven Traffic Forecasting](https://arxiv.org/pdf/1707.01926v3.pdf), *ICLR 2018*.
- [Revisiting Spatial-Temporal Similarity: A Deep Learning Framework for Traffic Prediction](https://arxiv.org/pdf/1803.01254.pdf), *AAAI 2019*.
- [Graph Attention Networks](https://arxiv.org/pdf/1710.10903v3.pdf), *ICLR 2018*.


- [ ] [Spatial-Temporal Fusion Graph Neural Networks for Traffic Flow Forecasting](https://arxiv.org/abs/2012.09641), *AAAI 2021*.

