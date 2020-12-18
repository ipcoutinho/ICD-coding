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

The code was tested with Pyhton 3.8.5 and Tensorflow 2.3.0.

# Training model

