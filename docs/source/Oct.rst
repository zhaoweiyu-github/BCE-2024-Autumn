Oct
===

Week 5-8
--------

During Weeks 5 to 8, your assignment is to fine-tune a pre-trained deep language model, such as `DNABERT <https://github.com/jerryji1993/DNABERT>`_ or `DNABERT-2 <https://github.com/MAGICS-LAB/DNABERT_2>`_, to perform binding prediction for CTCF binding sites from DNA sequences.

The format for the training and testing datasets—`train dataset (imbalanced) <https://github.com/zhaoweiyu-github/BCE-2024-Autumn/tree/main/docs/source/dataset/K562_CTCF_train_imbalance.csv>`_ and `test dataset (imbalanced) <https://github.com/zhaoweiyu-github/BCE-2024-Autumn/tree/main/docs/source/dataset/K562_CTCF_test_imbalance.csv>`_—is as follows:

.. code-block:: bash

   chrom,start,end,build_region_index,peak_k562:ctcf
   chr6,70413000,70414000,1670062,True
   chr4,25173000,25174000,1372412,True
   chr17,47890000,47891000,786861,True
   chr11,44656000,44657000,319623,False
   chrX,48430000,48431000,2087452,False

The first three columns represent genomic coordinates (``chromosome``, ``start``, ``end``), and the fifth column provides the binding event label (``True`` or ``False``).

This deep learning task aims to predict the label (``y``), where ``True`` indicates binding, and ``False`` indicates non-binding, based on the input DNA sequence (``x``). Below are the steps to complete the task:

1. Read the Paper and Understand Transformers
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   Read the `DNABERT paper <https://pubmed.ncbi.nlm.nih.gov/33538820/>`_ and explore the `DNABERT code <https://github.com/jerryji1993/DNABERT>`_ to understand the pre-training and fine-tuning process of deep language models. This foundational knowledge is critical for the following tasks.

2. Prepare the Code
   ~~~~~~~~~~~~~~~~

   Review and understand the DNABERT code, and load the pre-trained checkpoint to fine-tune it for the CTCF binding site prediction task.

3. Model Training and Evaluation
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   After preparing and testing your code, run it on GPU devices. You can access the school's HPC with GPUs by contacting Miss Yan Liu at yanliu@tongji.edu.cn. Train the fine-tuned model and evaluate its performance on the test dataset. 
   Note that the dataset is imbalanced, so carefully choose an appropriate loss function, such as focal loss, rather than a general cross-entropy loss, to improve training results.

.. note::

   You are expected to complete this task within two weeks (by November 1st) before proceeding to the next. However, if needed, you may extend the timeline to a month (by November 15th), feel free to contact me at zhaoweiyu@tongji.edu.cn.
