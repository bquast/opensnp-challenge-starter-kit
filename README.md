# opensnp-challenge-starter-kit
![CrowdAI-Logo](https://www.crowdai.org/assets/crowdai_head_no_background-a765964ef09bac4d057e4a2bacb3f1a28ee3457c9825f6490c78a80034eaf2e2.png)

Starter kit for getting started in the [CrowdAI OpenSNP Challenge](https://www.crowdai.org/challenges/opensnp-height-prediction).

# Installation
```
git clone https://github.com/spMohanty/opensnp-challenge-starter-kit
cd opensnp-challenge-starter-kit
pip install -r requirements.txt
pip install -U crowdai
```

# Data download and preparation
Download all the files from the [CrowdAI Dataset page](https://www.crowdai.org/challenges/opensnp-height-prediction/dataset_files),
and put them in the `data/` folder. Then :
```
cd data/
gunzip *.gz
```

**NOTE**: You might not need to download all the files, or even use all the files to come up with your predictions. It is recommended to use the `subset_cm_train.npy` and `train_heights.npy` to train your model, and use `subset_cm_test.npy` to make the predictions.

# Basic Usage

```
import crowdai
challenge = crowdai.Challenge("OpenSNPChallenge2017", "YOUR_CROWDAI_API_KEY_HERE")

data = ... #a list of 137 predicted heights for all the 137 corresponding data points in the test set
challenge.submit(data)
challenge.disconnect()
```

# Submit Random Predictions
```
python random_predict.py --api_key=<<YOUR_CROWDAI_API_KEY_HERE>>
```

# Predictions by Linear Regression
```
python linear_regression_predict.py --api_key=<<YOUR_CROWDAI_API_KEY_HERE>>
```

# Predictions by Support Vector Regression
```
python svr_predict.py --api_key=<<YOUR_CROWDAI_API_KEY_HERE>>
```

# Author
S.P. Mohanty <sharada.mohanty@epfl.ch>
