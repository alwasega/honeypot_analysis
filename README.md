# Analysis Honeypot Project

## Organization of the Repository


**data/**: Repository where data is expected to be stored locally

***.py**: Code to run the models. See the `Usage` section below.

**results/**: Results from running the models.

**stats/**: After training the VAE+DoSE-SVM benchmark, store the summary statistics for each trial in this directory. When testing, the VAE+DoSE-SVM benchmark expects five versions of the statistics to be recorded (seeds 1-5) in this directory to then calculated the anomaly predictions (using DoSE-SVM)



## Setup/Installation

After initializing a clean virtual environment with Python 3.8, use `requirements.txt` to install the necessary packages for our code to run:

```
pip install -r requirements.txt
```
For example, when using ```Conda```, follow the following steps: 

1. conda create --name myenv
2. conda activate myenv
3. conda deactivate (to deactivate myenv)

Stay at the highest level of the directory when running any of the following commands (see the `Usage` section below).


## Usage

For each of the following commands, the dataset is expected to be stored in `data/`. 

### Run a Benchmark

To train each of the anomaly detection models use the following command: 

```
python run_benchmark.py --train --benchmark dose 

# dose = VAE + DoSE-SVM
# rcov = Robust Covariance
# svm = One-Class SVM
# ifor = Isolation Forest
```

To test each model, swap the `--train` flag for `--test` and re-run.