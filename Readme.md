Model is available in HF [here](https://huggingface.co/AdrienB134/ColBERTv1.0-bert-based-spanish-mmarcoES/)

## Training

#### Details

The model is initialized from the [bert-base-spanish-wwm-uncased](https://huggingface.co/dccuchile/bert-base-spanish-wwm-uncased) checkpoint and fine-tuned on 10M triples via pairwise softmax cross-entropy loss over the computed scores of the positive and negative passages associated to a query. It was trained on a single Tesla A100 GPU with 40GBs of memory during 200k steps with 10% of warmup steps using a batch size of 96 and the AdamW optimizer with a constant learning rate of 3e-06. Total training time was around 12 hours.

#### Data

The model is fine-tuned on the Spanish version of the [mMARCO](https://huggingface.co/datasets/unicamp-dl/mmarco) dataset, a multi-lingual machine-translated version of the MS MARCO dataset.
The triples are sampled from the ~39.8M triples of [triples.train.small.tsv](https://microsoft.github.io/msmarco/Datasets.html#passage-ranking-dataset)
