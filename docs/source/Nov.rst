Nov
===

Weeks 9-12
----------

During Weeks 9 to 12, your assignment is to fine-tune `ChromBERT <https://github.com/TongjiZhanglab/ChromBERT>`_, a pre-trained deep language model developed by the Yong Zhang Lab, to predict genome-wide binding events for CTCF and EZH2.

The format for the training and testing datasets:

- `Training dataset for CTCF (imbalanced) <https://github.com/zhaoweiyu-github/BCE-2024-Autumn/tree/main/docs/source/dataset/K562_CTCF_train_imbalance.csv>`_
- `Testing dataset for CTCF (imbalanced) <https://github.com/zhaoweiyu-github/BCE-2024-Autumn/tree/main/docs/source/dataset/K562_CTCF_test_imbalance.csv>`_
- `Training dataset for EZH2 (imbalanced) <https://github.com/zhaoweiyu-github/BCE-2024-Autumn/tree/main/docs/source/dataset/hESC_EZH2_train_imbalance.csv>`_
- `Testing dataset for EZH2 (imbalanced) <https://github.com/zhaoweiyu-github/BCE-2024-Autumn/tree/main/docs/source/dataset/hESC_EZH2_test_imbalance.csv>`_

The format of these datasets is as follows:

.. code-block:: bash

   chrom,start,end,build_region_index,peak_k562:ctcf
   chr6,70413000,70414000,1670062,True
   chr4,25173000,25174000,1372412,True
   chr17,47890000,47891000,786861,True
   chr11,44656000,44657000,319623,False
   chrX,48430000,48431000,2087452,False

The first three columns represent genomic coordinates (``chromosome``, ``start``, ``end``), and the fifth column provides the binding event label (``True`` or ``False``).

This deep learning task aims to predict the label (``y``), where ``True`` indicates a binding event and ``False`` indicates non-binding, based on the input DNA sequence for DNABERT or binding status of cistromes for ChromBERT (``x``). Below are the steps to complete the task:

1. Read the Code and Understand ChromBERT
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   ChromBERT is pre-trained on a large-scale human ChIP-seq/DNase-seq/ATAC-seq dataset, **Cistrome-Human-6K**, through self-supervised learning. It is designed to learn robust, context-aware interactions of transcription regulators, enabling it to adapt to various downstream tasks and provide insights into context-specific transcription regulatory networks.

   You can explore the `code <https://github.com/TongjiZhanglab/ChromBERT>`_ and review the `tutorial for fine-tuning ChromBERT from scratch <https://chrombert.readthedocs.io/en/latest/tutorial_finetuning_ChromBERT_from_scratch.html>`_ for instructions on installing and fine-tuning the model. Ensure you understand each step and thoroughly review the basic code.

2. Fine-tune the Model Using Pre-trained Checkpoints
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   Prepare the input dataset for EZH2 and CTCF, and fine-tune the model for EZH2 and CTCF respectively.

3. Compare with DNA Sequence-Based Models such as DNABERT
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

   Evaluate the model's performance on the CTCF and EZH2 tasks, and compare the results from DNABERT and ChromBERT. Consider the factors that may contribute to differences in performance.

.. note::

   You are expected to complete this task within three weeks (by **Nov 21**). However, if needed, you may extend the timeline up to a month after finishing the last task (until **Dec 15**). For any questions or support, please contact me at zhaoweiyu@tongji.edu.cn.