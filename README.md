# ICD-coding

This work was developed in the context of a MSc thesis at Instituto Superior Técnico, University of Lisbon. Methods for automatic ICD coding, using a supervised machine learning approach, specifically a deep neural network, were already developed at Instituto Superior Técnico through a partnership with the Portuguese Directorate-General of Health (Direcção Geral da Saúde), envisioning the coding of death certificates (Duarte et al., 2018). This dissertation reports on extensions over that previous work, applying methodologies for automatic classification of full-text contents corresponding to hospital discharge summaries.

<pre><code>
@article{Duarte2018,
    author = {Duarte, Francisco and Martins, Bruno and Sousa, C{\'{a}}tia and Silva, M{\'{a}}rio J},
    journal = {Journal of Biomedical Informatics},
    title = {{Deep neural models for ICD-10 coding of death certificates and autopsy reports in free-text}},
    volume = {80},
    pages={64--77},
    year = {2018}
}
</code></pre>

Different alternatives of the baseline model are also reported, namely multi-label smoothing regularization, conjugating non-standard loss functions, different attention mechanisms, distinct strategies for initializing the weights of the final node of the network, Mogrifier LSTM (Melis et al., 2020) as an alternative recurrent unit, data augmentation, and pretrained word embeddings using the GloVe model (Pennington et al., 2014). The proposed multi-label smoothing strategy, leveraging the hierarchical structure of the ICD codes, and the adoption of dice loss, in specific the log-cosh Tvserky loss, in conjugation with the binary cross-entropy objective to address the data imbalance issue (Li et al., 2020), prove to be very effective in this classification task. Data augmentation, based on a back-translation process, and pretrained word embeddings are also incorporated into the full proposed model. 

<pre><code>
@inproceedings{Melis2020,
    author = {Melis, G{\'{a}}bor and Ko{\v{c}}isk{\'{y}}, Tom{\'{a}}{\v{s}} and Blunsomy, Phil},
    journal = {Proceedings of ICLR},
    pages = {1--13},
    title = {Mogrifier LSTM},
    year = {2020}
}
@article{Pennington2014,
    author = {Pennington, Jeffrey and Socher, Richard and Manning, Christopher D},
    title = {GloVe : Global Vectors for Word Representation},
    journal = {EMNLP},
    volume = {14},
    pages = {1532--1543},
    year = {2014}
}
@article{Li2020dice,
    author = {Li, Xiaoya and Sun, Xiaofei and Meng, Yuxian and Liang, Junjun and Wu, Fei and Li, Jiwei},
    journal = {arXiv preprint arXiv:1911.02855v2},
    title = {Dice Loss for Data-imbalanced NLP Tasks},
    year = {2020}
}
</code></pre>

The experiments were conducted on the MIMIC III dataset (Johnson et al., 2016), following splits of datasets made publicly available by Mullenbach et al. (2018).

The code was tested with Pyhton 3.8.5 and Tensorflow 2.3.0.

<pre><code>
@article{Johnson2016,
    author = {Johnson, Alistair E.W. and Pollard, Tom J. and Shen, Lu and Lehman, Li Wei H. and Feng, Mengling and Ghassemi, Mohammad and Moody, Benjamin and Szolovits, Peter     and {Anthony Celi}, Leo and Mark, Roger G.},
    journal = {Scientific Data},
    pages = {1--9},
    title = {MIMIC-III, a freely accessible critical care database},
    volume = {3},
    year = {2016}
}
@inproceedings{Mullenbach2018,
    author = {Mullenbach, James and Wiegreffe, Sarah and Duke, Jon and Sun, Jimeng and Eisenstein, Jacob},
    booktitle = {Proceedings of NAACL-HLT},
    pages = {1101--1111},
    title = {Explainable Prediction of Medical Codes from Clinical Text},
    year = {2018}
}
</code></pre>

# Training model

