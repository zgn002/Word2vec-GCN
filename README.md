# Word2vec-GCN

## Data:数据
 1）原始数据由于太大无法上传，请在Bingding Dataset官网自行下载：  
 2）bindingdb_data.ext:过滤后的数据  
 3）com_features.npz:使用Word2vec方法得到的100维化合物特征向量。  
 4）pro_features.npz:使用Word2vec方法得到的100维蛋白质特征向量。  
 5）neighbors_edge.npz:邻接矩阵  
 6）test_label.npz：测试集标签  
 7）train_label.npz:训练集标签  
 
 ## SPVec：Word2vec算法执行  

 ## graphsaint：GCN算法执行。
 layers.py: """
NOTE
    For the various GNN layers, we optionally support batch normalization. Yet, due to the
    non-IID nature of GNN samplers (whether it is graph-sampling or layer sampling based),
    we may need some modification to the standard batch-norm layer operations to achieve
    optimal accuracy on graphs.

    The study of optimal GNN-based batch-norm is out-of-scope for the current version of
    GraphSAINT. So as a compromise, we provide multiple implementations of batch-norm
    layer which can be optionally inserted at the output of the GNN layers.

Specifically, we have the various choices for the <bias> field in the layer classes
    'bias'          means no batch-norm is applied. Only add the bias to the hidden
                    features of the GNN layer.
    'norm'          means we calculate the mean and variance of the GNN hidden features,
                    and then scale the hidden features manually by the mean and variance.
                    In this case, we need explicitly create the 'offset' and 'scale' params.
    'norm-nn'       means we use the torch.nn.BatchNorm1d layer implemented by torch.
                    In this case, no need to explicitly maintain the BN internal params.
"""
 
 


 ## 基于表示学习的图神经网络模型预测化合物-蛋白质相互作用
