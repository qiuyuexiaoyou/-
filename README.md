# Tripartite GAN
This is the codes for the paper ''Tripartite GAN: A Reinforcement Learning Approach for Unsupervised Text Sentiment and Style Transfer''.
## Datasets
The Yelp and IMDb datasets can be found in the submitted .zip file.
Please unzip the folder "Data" into this folder "TriGAN".

To obtain the GYAFC Dataset, please contact the creator for access rights:

https://github.com/raosudha89/GYAFC-corpus

For ACL-ARC dataset, we used a clean version of it. 
It can be download from:

https://web.eecs.umich.edu/~lahiri/acl_arc.html

The ICLE dataset is available at:

https://corpora.uclouvain.be/cecl/icle/home

For all datasets, we filtered sentences with hapax legomenons and the maximum generation length is set to 20.
## Language Models
We pretrain language models for all used dataset by using KenLM. 

However, these pre-trained language model files are too large to upload. 

If you want to train a language model by yourself, please follow the steps at:

https://github.com/kpu/kenlm
## Quick Start
Step 1: Change the class Config in main.py

Step 2: Create a parallel data file

```python
python3 parallel_creater.py
```
Step 3: Pre-train a paraphrasing network and a style classifier

Step 4: Training the model

For the Step 3 and Step 4, please run the following code:
```python
python3 main.py
```

The outputs file will be created in the path "./save/".

The size of the parameter saved file of a trained model is approximately 248M.

We used the manual tuning to choose hyperparameter values. 
For the hyperparameters we used, please see the file "main.py" for details.
## Evaluation
To Evaluate our model, please run the following code:
```
cd evaluation
python3 evaluate.py
```
## Dependencies
```
python==3.8.5
numpy==1.19.4
nltk==3.5
sentence-transformers==0.4.0
torch==1.8.1
torchtext==0.9.1
kenlm
```
## Training Time
Generally speaking, on a single GPU (RTX 2080Ti), output file can be generated in an hour.

Nevertheless, the above pre-training steps will cost additional hours.
