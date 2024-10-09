# BR-Hunter

The code and dataset for the paper "BR-Hunter: Detect Information Types of Bug Reports from Online Community Discussions", implemented in Pytorch. The method named BR-Hunter, which comprises the following four components. Specifically,the data preprocessing component disentangles and denoises the live chats, while the utterance embedding component aims to extract the semantic features of each utterance in the conversation. The bug report identification component then models the conversation as
a feature graph and uses GAT and GNN_FiLm to identify conversations containing bug reports. Finally, the bug report synthesis component classifying and reassembling sentences in conversations containing bug report by fine-tuning BERT and prompt learning methods.

## 1. Project Structure
- `data/`
	- `*_train.json :training conversations dataset`
	- `*_test.json :tseting conversations dataset`
- `data preparation/ :code for data preparation, including synonym replacement, etc.`
- `dataloader.py : dataset reader for BR-Hunter`
- `model.py : BR-Hunter model`
- `FocalLoss.py : focal loss function`
- `train.py : a file for model training`

## 2. Environment Setup

The code is tested with Python 3.7. All dependencies are listed in [requirements.txt](requirements.txt).

## 3. Data preparation
The data is stored in the "data" folder. The training dataset should be named in the format of project name + "_train.json" and put it in the folder `data/train/`. 
The testing dataset should be named in the format of project name + "_test.json" and put it in the folder `data/test/`.


## 4. Usage
When your dataset is ready in the previous step, you can go to the "train.py" to modify the name of the "project", and you can modify config parameters through "Config" class. Finally, start the code by command.


```
python train.py
```

## Citation

If you find the code useful, please cite our paper.
```

```

## Contact

For any questions, please drop an email to Shikai Guo.
