Sep
===

Week 3~4
--------

During Weeks 3 and 4, your assignment is to develop a machine learning model to predict CTCF binding events from DNA sequences.

The format of the `train dataset <dataset/K562_CTCF_train.csv>`_ and `test dataset <dataset/K562_CTCF_test.csv>`_ is as follows:

.. code-block:: bash

   chrom,start,end,build_region_index,peak_k562:ctcf
   chr6,70413000,70414000,1670062,True
   chr4,25173000,25174000,1372412,True
   chr17,47890000,47891000,786861,True
   chr11,44656000,44657000,319623,False
   chrX,48430000,48431000,2087452,False

The first three columns represent the genomic coordinates (``chromosome``, ``start``, ``end``), and the fifth column provides the binding events label (``True`` or ``False``).

This machine learning task aims to predict the label (``y``), where ``True`` indicates binding and ``False`` indicates non-binding, from the input DNA sequence (``x``). Below are the steps to complete the task:

1. Input Feature Preparation
   ~~~~~~~~~~~~~~~~~~~~~~~~~

   You are required to extract the DNA sequences corresponding to CTCF binding events on the human genome. To achieve this, write a Python script that reads DNA sequences from the genomic coordinates. You can use the `twobitreader <https://pythonhosted.org/twobitreader/twobitreader.html>`_ package to access the DNA sequences from the `human hg38 genome <https://hgdownload.cse.ucsc.edu/goldenpath/hg38/bigZips/>`_.

2. Input Feature Engineering
   ~~~~~~~~~~~~~~~~~~~~~~~~~

   Feature engineering is a critical step in this task. Consider how you will transform the input DNA sequences into features that can be fed into the model. A simple approach is to treat the 1-kb DNA sequences as 1,000 individual features. However, you are encouraged to explore more sophisticated encoding methods, especially considering that the CTCF binding motif typically spans more than 10 base pairs. A thoughtful encoding strategy could improve model performance.

3. Model Training and Evaluation
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   Once you have prepared your features, apply a random forest classifier to predict the binding label (``y``, where 1 represents binding and 0 represents non-binding). Train the model on the provided training dataset, and evaluate its performance on the test dataset. Be sure to calculate the relevant evaluation metrics on the test data to assess your model's effectiveness.

Optional (not required):

   If you are interested, you may attempt to use a convolutional neural network (CNN) to complete this task.

.. note::

   This task is due on September 30. Please send your Python code or Jupyter notebook via e-mail at zhaoweiyu@tongji.edu.cn or share it through a private GitHub repository.
   

Week 1~2
--------

In the first week, please read the paper titled `Predicting the sequence specificities of DNA- and RNA-binding proteins by deep learning <https://doi.org/10.1038/nbt.3300>`_, which introduces a deep learning method for predicting transcription factor binding.

Additionally, familiarize yourself with the basic concepts in machine learning by engaging in Python code practice. Here are specific sections to focus on:

1. Data Preprocessing, as described in `section 6.3 <https://scikit-learn.org/stable/modules/preprocessing.html>`_ of the ``scikit-learn`` user guide.

2. Implementation of classical machine learning models, specifically decision trees, in `section 1.10 <https://scikit-learn.org/stable/modules/tree.html>`_ of the ``scikit-learn`` user guide.

3. Implementation of evaluation metrics to measure model performance in classification tasks, detailed in `section 3.4.2 <https://scikit-learn.org/stable/modules/model_evaluation.html>`_ of the ``scikit-learn`` user guide.

After studying these materials, attempt to build machine learning models for a classification task using scikit-learn with the dataset provided by the package. Experiment with multiple machine learning models and compare their performance using the evaluation metrics.

Optional (not required):

1. If you are interested, after completing the above tasks, you can begin to explore the basics and implementation of deep learning models using ``PyTorch``. Start with the `video series by Dr. Li <https://space.bilibili.com/1567748478/channel/seriesdetail?sid=358497>`_. The initial sections should now be accessible to you.

.. note::

   You may use ChatGPT or any other artificial intelligence language model applications to assist you with these tasks. However, ensure that you understand each step of the learning process.

   If you have any questions, please feel free to contact me at zhaoweiyu@tongji.edu.cn.

