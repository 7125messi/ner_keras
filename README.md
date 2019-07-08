## requirements 
* tensorflow=1.14.0
* keras=2.2.4
* keras-contrib=2.0.8
  * pip install git+https://www.github.com/keras-team/keras-contrib.git
* h5py 
* pickle


## train

```shell
python train.py
```

如下所示：
```
(nlp) [zhaoyadong@21:35:54]~/opt/git/ner_keras/code$ python train.py
Using TensorFlow backend.
WARNING: Logging before flag parsing goes to stderr.
W0708 21:36:10.683329 4740908480 deprecation_wrapper.py:119] From /Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py:74: The name tf.get_default_graph is deprecated. Please use tf.compat.v1.get_default_graph instead.

W0708 21:36:10.693880 4740908480 deprecation_wrapper.py:119] From /Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py:517: The name tf.placeholder is deprecated. Please use tf.compat.v1.placeholder instead.

W0708 21:36:10.694991 4740908480 deprecation_wrapper.py:119] From /Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py:4138: The name tf.random_uniform is deprecated. Please use tf.random.uniform instead.

W0708 21:36:10.874849 4740908480 deprecation.py:323] From /Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py:2974: add_dispatch_support.<locals>.wrapper (from tensorflow.python.ops.array_ops) is deprecated and will be removed in a future version.
Instructions for updating:
Use tf.where in 2.0, which has the same broadcast rule as np.where
W0708 21:36:11.172960 4740908480 deprecation_wrapper.py:119] From /Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py:133: The name tf.placeholder_with_default is deprecated. Please use tf.compat.v1.placeholder_with_default instead.

_________________________________________________________________
Layer (type)                 Output Shape              Param #
=================================================================
embedding_1 (Embedding)      (None, None, 200)         851600
_________________________________________________________________
bidirectional_1 (Bidirection (None, None, 200)         240800
_________________________________________________________________
crf_1 (CRF)                  (None, None, 7)           1470
=================================================================
Total params: 1,093,870
Trainable params: 1,093,870
Non-trainable params: 0
_________________________________________________________________
/Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras_contrib/layers/crf.py:346: UserWarning: CRF.loss_function is deprecated and it might be removed in the future. Please use losses.crf_loss instead.
  warnings.warn('CRF.loss_function is deprecated '
/Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras_contrib/layers/crf.py:353: UserWarning: CRF.accuracy is deprecated and it might be removed in the future. Please use metrics.crf_accuracy
  warnings.warn('CRF.accuracy is deprecated and it '
W0708 21:36:11.181104 4740908480 deprecation_wrapper.py:119] From /Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras/optimizers.py:790: The name tf.train.Optimizer is deprecated. Please use tf.compat.v1.train.Optimizer instead.

W0708 21:36:12.741391 4740908480 deprecation_wrapper.py:119] From /Users/zhaoyadong/anaconda3/envs/nlp/lib/python3.6/site-packages/keras/backend/tensorflow_backend.py:986: The name tf.assign_add is deprecated. Please use tf.compat.v1.assign_add instead.

Train on 50658 samples, validate on 4631 samples
Epoch 1/3
2019-07-08 21:36:12.982749: I tensorflow/core/platform/cpu_feature_guard.cc:142] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
50658/50658 [==============================] - 493s 10ms/step - loss: 4.0671 - crf_viterbi_accuracy: 0.9519 - val_loss: 7.8890 - val_crf_viterbi_accuracy: 0.9700
Epoch 2/3
50658/50658 [==============================] - 486s 10ms/step - loss: 3.9722 - crf_viterbi_accuracy: 0.9779 - val_loss: 7.8681 - val_crf_viterbi_accuracy: 0.9743
Epoch 3/3
50658/50658 [==============================] - 532s 10ms/step - loss: 3.9585 - crf_viterbi_accuracy: 0.9836 - val_loss: 7.8593 - val_crf_viterbi_accuracy: 0.9782
```



## demo 

```shell
python val.py
```
 

input:
```text
中华人民共和国国务院总理周恩来在外交部长陈毅,
副部长王东的陪同下，
连续访问了埃塞俄比亚等非洲10国以及阿尔巴尼亚
```
output:
```python
['person: 周恩来 陈毅, 王东', 'location: 埃塞俄比亚 非洲 阿尔巴尼亚', 'organzation: 中华人民共和国国务院 外交部']
```





