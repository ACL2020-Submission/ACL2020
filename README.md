# ACL 2020 Submission
## Abstract
The Sumerian cuneiform writing script was invented more than 5,000 years ago and represents one of the oldest in history. In this paper, we present the first attempt of its kind to automatically translate between Sumerian and English text fragments. We release high-quality corpora for training and evaluation and report results on experiments with two different encoder-decoder architectures for translation. Our proposed methodology, in particular the attention visualizations obtained from the translation model, enable expert archaeologists to automate costly and time-consuming manual translations and assist them in better determining the meaning of a piece of Sumerian text.

## Project Update
Project is completed with implementing 3 different Neural Network architecture for Machine Translation task.

## Installation
Clone the repository. (We are assuming you have python version 3.6.x and pip is installed on your linux system)

(Optional)If not, please use the below command, this will create a new environment using conda.
```bash
conda create -n cdli python=3.6
conda activate cdli
```

All dependencies can be installed via:

```bash
pip install -r requirements.txt
```
NOTE: If you have MemoryError in the install try to use:

```bash
pip install -r requirements.txt --no-cache-dir
```

Note that Project currently support PyTorch >= 1.1 (should be work with 1.0)

By this point, your system should be ready with all dependencies. Please use below command to check PyTorch verion.
```bash
python -c "import torch; print(torch.__version__)"
```
Output should be your PyTorch version >= 1.1.0

If you still face any issues while installing dependencies for the project, feel free to ping us at our [Communication channel](https://cdli-gsoc.slack.com/).

## Quickstart
Please refer to [Full Documentation](http://opennmt.net/OpenNMT-py/) of OpenNMT once before starting.

### Translation Results

Translation results are available in translation_results folder for all Neural Network Architecture. For more details about Neural Network architecture and details, feel free to contact us on CDLI [Communication Channel](https://cdli-gsoc.slack.com/).


### Translating new Data

Please use the below command to translate new Sumerian phrase to English phrase. We are assuming you have a text file placed in data folder as **sumerian_test.txt**.

```bash
python3 translate.py -model trained_models/baseline_model.pt -src data/sumerian_test.txt -output pred.txt -replace_unk -verbose
```

Now you have a model which you can use to predict on new data. We do this by running beam search. This will output predictions into `pred.txt`.

## License
This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/cdli-gh/Machine-Translation/blob/master/LICENSE.md) file for details.
