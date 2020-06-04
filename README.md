# Bert Distillation

[![CodeFactor](https://www.codefactor.io/repository/github/pussymipt/bert-distillation/badge)](https://www.codefactor.io/repository/github/pussymipt/bert-distillation)
![codestyle](https://github.com/PUSSYMIPT/bert-distillation/workflows/CI/badge.svg?branch=master&event=push)


## Main repo and feature works

Main repo can be found [here](https://github.com/PUSSYMIPT/bert-distillation).

## Features

- distributed training
- logging with tensorboard, wandb, neptune, alchemy ...
- fp16
- various losses and loss agregating
- initialization with teacher's layers

## Experiment && Results

I initialize my model with \[0,2,4,7,9,11\] encoder layers of teacher model.

I ran my script for 100 hours on 4x1080TI with RuBERT model as a teacher. Logs can be found [here](https://app.wandb.ai/torchwave/bert-distillation). I distil it on Lenta Russian News dataset.

Then I run classification task on mokoron twitter [dataset](http://study.mokoron.com/).

Here are my results:

![Experiment results](https://i.ibb.co/pK6SZD3/newplot-37.png)

My models can 

## Post

Also, probably soon, I will publish my post about my project on medium (in pytorch blog). Here is a draft [link](https://medium.com/@nikitabalagansky/bert-distillation-with-catalyst-c6f30c985854). Thanks to Sergey Kolesnikov from catalyst-team for promotion.

Feel free to propose something new for this project.

## Folders

1. `bin` - bash files for running pipelines
2. `configs` - just place configs here
3. `docker` - project Docker files for pure reproducibility
4. `presets` - datasets, notebooks, etc - all you don't need to push to git
5. `requirements` - different project python requirements for docker, tests, CI, etc
6. `scripts` - data preprocessing scripts, utils, everything like `python scripts/.py`
7. `serving` - microservices, etc - production
8. `src` - model, experiment, etc - research

## Usage
```
git clone https://github.com/PUSSYMIPT/bert-distillation.git
cd bert-distillation
pip install -r requirements/requirements.txt
bin/download_lenta.sh
python scripts/split_dataset.py --small
catalyst-dl run -C configs/config_ru_ranger.yml --verbose --distributed
```
It will take a lot of time. "Let's go get some drinks"
