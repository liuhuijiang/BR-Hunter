# BR-Hunter

The code and dataset for the paper "BR-Hunter: Detect Information Types of Bug Reports from Online Community Discussions", implemented in Pytorch.

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

## 5. Implementation guidance
Finally, if you want to apply the trained model to actual scenarios, you need to choose a suitable deployment method to encapsulate the model into an API, such as Flask. A brief tutorial on using flask is as follows:

First, install the necessary libraries.

```
pip install torch flask Pillow
```

Second, save the model

```
torch.save(model.state_dict(), 'model_path.pth')
```

3. Package into interface

```
model.load_state_dict(torch.load('model_path.pth'))
app = Flask(__name__)
@app.route('/predict', methods=['POST'])
def predict():
    # Preprocessing Input
    output = model(input)
    prediction = torch.argmax(output, dim=1)
    # return prediction results
 ```

4. Use the format corresponding to the API to call

## Citation

If you find the code useful, please cite our paper.
```

```

## Contact

For any questions, please drop an email to Shikai Guo.
