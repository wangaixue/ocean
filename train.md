# Training tutorial

#### prepare data
Please download training data from [here](https://drive.google.com/drive/folders/1ehjVhg6ewdWSWt709zd1TkjWF7UJlQlq?usp=sharing).

#### prepare pretrained model
Please download the pretrained model on ImageNet [here](https://drive.google.com/open?id=1Pwe5NRdOoGiTYlnrOZdL-3S494RkbPQe), and then put it in `pretrain`.

#### modify settings
Please modify the training settings in `experiments/train/ocean.yaml`. The default number of GPU and batch size in paper are 8 and 32 respectively. 

#### run
```
python ocean_tracking/onekey.py
```
This script integrates **train**, **epoch test** and **tune**. It is suggested to debug/run them one by one when you are not familiar with our whole framework (modify the key `ISTRUE` in `experiments/train/ocean.yaml`). When you know this framework well, simply intergrate your idea and run this one-key script.