# Relational-GCN

* Paper: [https://arxiv.org/abs/1703.06103](https://arxiv.org/abs/1703.06103)
* Author's code for entity classification: [https://github.com/tkipf/relational-gcn](https://github.com/tkipf/relational-gcn)
* Author's code for link prediction: [https://github.com/MichSchli/RelationPrediction](https://github.com/MichSchli/RelationPrediction)

### Prerequisites
Two extra python packages are needed for this example: 

- rdflib
- pandas

Example code was tested with rdflib 4.2.2 and pandas 0.23.4

### Entity Classification
AIFB: accuracy 97.22% (DGL), 95.83% (paper)
```
DGLBACKEND=mxnet python entity_classify.py -d aifb --testing --gpu 0
```

MUTAG: accuracy 76.47% (DGL), 73.23% (paper)
```
DGLBACKEND=mxnet python entity_classify.py -d mutag --l2norm 5e-4 --n-bases 40 --testing --gpu 0
```

BGS: accuracy 79.31% (DGL, n-basese=20, OOM when >20), 83.10% (paper)
```
DGLBACKEND=mxnet python entity_classify.py -d bgs --l2norm 5e-4 --n-bases 20 --testing --gpu 0 --relabel
```
