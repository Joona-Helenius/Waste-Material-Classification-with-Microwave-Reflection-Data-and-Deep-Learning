# Waste Material Classification with Wicrowave Reflection Data and Deep Learning

Readme is a work in progress and will be filled out with more details in the future.

Joona Helenius
Master's thesis can be found [here](https://www.utupub.fi/handle/10024/194492).

The code used in my master's thesis in the University of Turku that has been modified slightly in preparation of publication. The performance of DNN models are tested on a custom dataset of microwave reflections taken from cardboard, plastic and metal objects to assess if microwave reflections contain information that could be used to identify the object material using machine learning. 

## Dataset
The dataset for the experiment was measured using two [LAIRD Technologies panel antennae](https://gatewayrfidstore.com/product_images/Antenna/laird_indoor_etsi_specs.pdf ) with one acting as the transmitter and the other as the receiver. These antennae were were connected to a [nanoVNA-F V2](https://www.sysjoint.com/index.php?tpl=product_detail&pid=11&uid=17&id=65&sno=1&list=2&lang=en) that measured the reflection and forward transmission coefficients of the microwave signal that was directed towards the measured objects by the transmitting antenna and the portion of the signal that was reflected into the receiving antenna. Each object was measured in multiple orientations to account for the effects of radio cross-section. All in all 97 objects were measured of which 34, 33 and 30 were metal, plastic and cardboard objects respecively. The total size of the dataset was 1112 .s2p-files containing the real-imaginary value pairs of the transmission and reflection coefficients for 101 distinct measurement points over the frequency range 863-879 MHz.

## Files
Four different data configurations were selected and for each of these configurations two rounds of hyperparameter optimization were performed using deep neural networks. Each ML.ipynb file contains the full hyperparameter optimization process and performance evaluation for one data configurations. The data configurations themselves are as follows: 
  1. Binary classification with random data split
  2. Binary classification with item-based data split
  3. Multiclass classification with random data split
  4. Multiclass classification with item-based data split

In binary classification the model is used to only classify between non-metal and metal samples and in item-based splitting the data is split such that all .s2p-files measured from one object are only present in one of the three partitions of the data used in training (train, validation, test).

In addition to the ML training files .ipynb-file used for data exploration is also included in this repository.
