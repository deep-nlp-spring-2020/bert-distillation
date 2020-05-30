# Bert Distillation

[![CodeFactor](https://www.codefactor.io/repository/github/pussymipt/bert-distillation/badge)](https://www.codefactor.io/repository/github/pussymipt/bert-distillation)
![codestyle](https://github.com/PUSSYMIPT/bert-distillation/workflows/CI/badge.svg?branch=master&event=push)


## Main repo and feature works

Main repo can be found [here](https://github.com/PUSSYMIPT/bert-distillation).

#### Feature Works

Soon will come catalyst 20.6 update with some core changes and LanguageModelingDataset (which was contributed by me). So the main repo will be updated.

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

### Docker

I also add dockerfile.
```
git clone https://github.com/PUSSYMIPT/bert-distillation.git
cd bert-distillation
docker build -f docker/Dockerfile  # yields container id
docker run {your container id}
```


## Contribution

1. Clone repository
2. run `pip install -r requirements/requirements-dev.txt -r requirements/requirements.txt`
3. write some code
4. run `catalyst-make-codestyle`
5. run `catalyst-check-codestyle`
6. if exit code is not 0 refactor your code
7. commit!
