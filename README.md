## requirements 
* tensorflow=1.14.0
* keras=2.2.4
* keras-contrib=2.0.8
  * pip install git+https://www.github.com/keras-team/keras-contrib.git
* h5py 
* pickle

## demo 

```python
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





