# Deopen
A hybrid deep convolutional neural network for predicting chromatin accessibility

# Requirements
- h5py
- hickle
- Scikit-learn=0.18.2
- Theano=0.8.0
- Lasagne=0.2.dev1
- nolearn=0.6.0

# Instructions

 
```java
# Data preprocessing and preparation

python Gen_data.py [options] -in <inputfile> -out <outputfile>

Arguments:
 inputfile: peak file generated by HotSpot algorithum (bed format)
 outputfle: preprocessed file containing different features (hkl format)
 
Options:
 -l <int> length of sequence (default: 1000)
 -s <int> number of samples (default: 100000)

# Run Deopen classification model

THEANO_FLAGS='device=gpu,floatX=float32' python Deopen_classification.py -in <inputfile> -out <outputfile>

Arguments:
 inputfile: preprocessed file containing different features (hkl format)
 outputfile: trained model to be saved (hkl format)

# Run Deopen regression model

THEANO_FLAGS='device=gpu,floatX=float32' python Deopen_regression.py -in <inputfile> -reads <readsfile> -out <outputfile>

Arguments:
 inputfile: preprocessed file containing different features (hkl format)
 readsfile: reads count for each sample (hkl format)
 outputfile: trained model to be saved (hkl format)

```


# License
This project is licensed under the MIT License - see the LICENSE.md file for details
