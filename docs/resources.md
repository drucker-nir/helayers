#### News
- 2020 Jan 10,  <font size=3>[Top Brazilian Bank Pilots Privacy Encryption Quantum Computers Can’t Break](https://ibm-research.medium.com/top-brazilian-bank-pilots-privacy-encryption-quantum-computers-cant-break-92ed2695bf14)</font>

#### Blogs
<a href="https://developer.ibm.com/blogs/secure-ai-workloads-using-fully-homomorphic-encrypted-data/" target=”_blank”>IBM Developer Blog</a>

#### Tile Tensors

- <font size=3>HElayers: A Tile Tensors Framework for Large Neural Networks on Encrypted Data. [[arXiv](https://arxiv.org/abs/2011.01805), [PETs 2023](https://petsymposium.org/popets/2023/popets-2023-0020.php)]
- Complex Encoded Tile Tensors: Accelerating Encrypted Analytics. [[IEEE Security and Privacy](https://ieeexplore.ieee.org/document/9805391)]</font>
- Advanced homomorphic encryption packing methods with applications to machine learning. [[CCS 2022 Tutorial webpage](https://research.ibm.com/haifa/dept/vst/tutorial_ccs2022.html)].</font>

#### HE-Friendly neural networks

- <font size=3>A methodology for training homomorphic encryption friendly neural networks [[arXiv](https://arxiv.org/abs/2111.03362), [SIMLA 2022](https://link.springer.com/chapter/10.1007/978-3-031-16815-4_29)]
- HE-PEx: Efficient Machine Learning under Homomorphic Encryption using Pruning, Permutation and Expansion [[arXiv](https://arxiv.org/abs/2207.03384)].
- Secure SqueezeNet inference in 4 minutes. 43rd IEEE Symposium on Security and Privacy [[s&p 2022 posters](https://www.ieee-security.org/TC/SP2022/program-posters.html), [pdf](https://www.ieee-security.org/TC/SP2022/downloads/SP22-posters/sp22-posters-50.pdf)].</font>


#### FHE Theory
- <font size=3> BLEACH: Cleaning Errors in Discrete Computations over CKKS [[ePrint](https://eprint.iacr.org/2022/1298)].</font>

#### Implementations optimization and security

- <font size=3>Timing leakage analysis of non-constant-time NTT implementations with Harvey butterflies [[ePrint](https://eprint.iacr.org/2022/094),  [CSCML 2022](https://link.springer.com/chapter/10.1007/978-3-031-07689-3_8)].
- NTT software optimization using an extended Harvey butterfly [[ePrint](https://eprint.iacr.org/2021/1396)].</font>

#### Privacy-Preserving Record Linkage

- <font size=3>Privacy-preserving record linkage using local sensitive hash and private set intersection [[arXiv](https://arxiv.org/abs/2203.14284), [Cloud & Security 2022](https://link.springer.com/chapter/10.1007/978-3-031-16815-4_22)].</font>

## Tutorials references

Some of the [tutorials](demos.md) that HElayers provide are based on prior-art data or on public datasets, which are listed below.

### Public Datasets

| Dataset |  <div style="min-width:250px">Description</div> |  <div style="min-width:250px">Reference</div> |
|---------|-------------|-----------|
| Adult  | Predict whether income exceeds $50K/yr based on census data. Also known as "Census Income" dataset. Number of Instances: 48842. Number of Attributes: 14 | Kohavi, R., Becker, B.: Uci machine learning repository: adult dataset (1996), [Link](https://archive.ics.uci.edu/ml/datasets/adult)|
| Iris    | Famous database; from Fisher, 1936. Number of Instances: 150. Number of Attributes: 4 | C. L. Blake and C. J. Merz, UCI Repository of machine learning databases: iris dataset [Link](https://archive.ics.uci.edu/ml/datasets/iris)|
| ImageNet | an image database organized according to the WordNet hierarchy (currently only the nouns), in which each node of the hierarchy is depicted by hundreds and thousands of images. Image-size: 224x224x3 | [Link](https://www.image-net.org/about.php) |
| MNIST   | The MNIST database of handwritten digits, has a training set of 60,000 examples, and a test set of 10,000 examples. Image size: 28x28x1 | LeCun, Yann and Cortes, Corinna. "MNIST handwritten digit database." [Link](http://yann.lecun.com/exdb/mnist/) (2010)|
| Newsgroups | This data set consists of 20000 messages taken from 20 Usenet newsgroups. | The UCI KDD Archive Information and Computer Science University of California, Irvine , [Link](http://kdd.ics.uci.edu/databases/20newsgroups/20newsgroups.html) |

### Neural Network Architectures

| Network name | Reference |
|--------------|-----------|
| AlexNet (Variant 1) | Krizhevsky, Alex and Sutskever, Ilya and Hinton, Geoffrey E. "Imagenet classification with deep convolutional neural networks", Advances in neural information processing systems 25, 2012.|
| CryptoNets | Gilad-Bachrach, R., Dowlin, N., Laine, K., Lauter, K., Naehrig, M. & Wernsing, J.. (2016). CryptoNets: Applying Neural Networks to Encrypted Data with High Throughput and Accuracy. Proceedings of The 33rd International Conference on Machine Learning, in Proceedings of Machine Learning Research 48:201-210 Available [here](https://proceedings.mlr.press/v48/gilad-bachrach16.html). |
| SqueezeNet | Forrest N. Iandola and Song Han and Matthew W. Moskewicz and Khalid Ashraf and William J. Dally and Kurt Keutzer, "SqueezeNet: AlexNet-level accuracy with 50x fewer parameters and <0.5MB model size", 2016, [link](https://arxiv.org/abs/1602.07360). | 
| ResNet | Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun; Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2016, pp. 770-778 [link](https://openaccess.thecvf.com/content_cvpr_2016/html/He_Deep_Residual_Learning_CVPR_2016_paper.html) |

#### Credit card fraud detection using NN inference

- Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015

- Dal Pozzolo, Andrea; Caelen, Olivier; Le Borgne, Yann-Ael; Waterschoot, Serge; Bontempi, Gianluca. Learned lessons in credit card fraud detection from a practitioner perspective, Expert systems with applications,41,10,4915-4928,2014, Pergamon

- Dal Pozzolo, Andrea; Boracchi, Giacomo; Caelen, Olivier; Alippi, Cesare; Bontempi, Gianluca. Credit card fraud detection: a realistic modeling and a novel learning strategy, IEEE transactions on neural networks and learning systems,29,8,3784-3797,2018,IEEE

- Dal Pozzolo, Andrea Adaptive Machine learning for credit card fraud detection ULB MLG PhD thesis (supervised by G. Bontempi)

- Carcillo, Fabrizio; Dal Pozzolo, Andrea; Le Borgne, Yann-Aël; Caelen, Olivier; Mazzer, Yannis; Bontempi, Gianluca. Scarff: a scalable framework for streaming credit card fraud detection with Spark, Information fusion,41, 182-194,2018,Elsevier

- Carcillo, Fabrizio; Le Borgne, Yann-Aël; Caelen, Olivier; Bontempi, Gianluca. Streaming active learning strategies for real-life credit card fraud detection: assessment and visualization, International Journal of Data Science and Analytics, 5,4,285-300,2018,Springer International Publishing

- Bertrand Lebichot, Yann-Aël Le Borgne, Liyun He, Frederic Oblé, Gianluca Bontempi Deep-Learning Domain Adaptation Techniques for Credit Cards Fraud Detection, INNSBDDL 2019: Recent Advances in Big Data and Deep Learning, pp 78-88, 2019

- Fabrizio Carcillo, Yann-Aël Le Borgne, Olivier Caelen, Frederic Oblé, Gianluca Bontempi Combining Unsupervised and Supervised Learning in Credit Card Fraud Detection Information Sciences, 2019

- Yann-Aël Le Borgne, Gianluca Bontempi Machine Learning for Credit Card Fraud Detection - Practical Handbook

#### Heart disease detection using NN inference
- https://archive.ics.uci.edu/ml/datasets/Heart+Disease

- Detrano, R., Janosi, A., Steinbrunn, W., Pfisterer, M., Schmid, J., Sandhu, S., Guppy, K., Lee, S., & Froelicher, V. (1989). International application of a new probability algorithm for the diagnosis of coronary artery disease. American Journal of Cardiology, 64,304--310.

- David W. Aha & Dennis Kibler. "Instance-based prediction of heart-disease presence with the Cleveland database."

- Gennari, J.H., Langley, P, & Fisher, D. (1989). Models of incremental concept formation. Artificial Intelligence, 40, 11--61.

#### Completely Random Forest

- Aslett, Louis JM, Pedro M. Esperança, and Chris C. Holmes. "Encrypted statistical machine learning: new privacy preserving methods." arXiv preprint arXiv:1508.06845 (2015).

