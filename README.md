# An encoder-decoder deep learning approach for multistep service traffic prediction

## General Info

In this repository, we compare statistical time series with Deep Learning (DL) models. We propose an **encoder-decoder DL approach** for multi-step traffic prediction. 

What makes **encoder-decoder** models an ideal candidate for sequence-to-sequence prediction is their inherit ability to map sequences of different lengths to each other. This functionality is the result of the model’s architecture. The encoder takes the input sequence and represent the information as latent variables. The decoder is set to the final states
of the encoder and trained to generate the output based on the information gathered by the encoder.

We examined four encoder-decoder DL architectures:

 - Stacked LSTMs  
 - CNN-LSTMs  
 - Bidirectional LSTM  
 - an innovative Hybrid Unidirectional-Bidirectional LSTM

![encoder-decoder](https://github.com/f-coda/Encoder_Decoder-DL/assets/23379126/ce566c88-8191-41cd-94f8-4de9c21fbd04)

**Hybrid Unidirectional-Bidirectional LSTM**

This novel architectural paradigm is the product of utilizing both bidirectional and unidirectional LSTMs instead of just one of the two. The input layer is a bidirectional LSTM. A unidirectional LSTM layer is then stacked on top of the bidirectional one. The bidirectional layer will provide one hidden state output for each time-step in 3-dimensional
form which is then utilized as input by the unidirectional layer. The core idea behind this architectural choice is the fact that by introducing heterogeneous layers the model will be able to exploit the temporal correlations present in the various time-series in a more sophisticated way when compared to the rest of the models. Furthermore the fact that
multiple layers are being utilized allows the features of the input sequence to be represented in a more robust way. The same design logic is implemented in the decoder part in order to mirror the encoder morphology. Instead of the basic LSTM model used in the previously explored decoders, the Hybrid model utilizes a bidirectional layer stacked on top of a unidirectional layer. This structural symmetry enables the decoder to properly reconstruct the underlying temporal motifs of the input sequence.

**Dataset description**

We conducted experiments using a [TCP trace data set](https://ita.ee.lbl.gov/html/contrib/LBL-CONN-7.html) with a 5 minutes time-step. We predict the number of requests, the transmitted data and the duration of the sessions with multi-steps in a range of one to five steps, which corresponds to a time window that spans 25 minutes in total.

## Cite Us

If you use the above code for your research, please cite our papers:

- [An encoder-decoder deep learning approach for multistep service traffic prediction](https://ieeexplore.ieee.org/document/9564320)
     
      @inproceedings{theodoropoulos2021encoder,
      title={An encoder-decoder deep learning approach for multistep service traffic prediction},
      author={Theodoropoulos, Theodoros and Maroudis, Angelos-Christos and Violos, John and Tserpes, Konstantinos},
      booktitle={2021 IEEE Seventh International Conference on Big Data Computing Service and Applications (BigDataService)},
      pages={33--40},
      year={2021},
      organization={IEEE}
      }

