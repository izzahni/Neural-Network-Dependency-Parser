## NEURAL NETWORK DEPENDENCY PARSER
This is a Neural Network Dependency Parser using TensorFlow based on the paper  
[A Fast and Accurate Dependency Parser using Neural Networks](https://www.aclweb.org/anthology/D14-1082.pdf)  

#### REQUIREMENTS
1. Python 3.5–3.8  
   - I'm using [python 3.7.7](https://www.python.org/downloads/release/python-377/)
2. Pip 19.0 or later (requires manylinux2010 support)
   - I'm using [pip 20.1](https://pip.pypa.io/en/stable/)
3. Operation System
   - Ubuntu 16.04 or later (64-bit)
   - MacOS 10.12.6 (Sierra) or later (64-bit) (no GPU support)
   - Windows 7 or later (64-bit) and [Microsoft Visual C++ Redistributable for Visual Studio 2015, 2017 and 2019](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)
     - I'm using windows 10
   - Raspbian 9.0 or later
4. GPU support requires a CUDA®-enabled card (Ubuntu and Windows)
   - I'm using [CUDA 10.2](https://developer.nvidia.com/cuda-downloads) and [cuDNN 7.6.5](https://developer.nvidia.com/rdp/cudnn-download)
5. Tensorflow and Tensorflow-gpu
   - I'm using [Tensorflow 1.15](https://www.tensorflow.org/install/pip) and [Tensorflow-gpu 1.15](https://www.tensorflow.org/install/pip)
     - Install using command prompt  
       `pip install tensorflow==1.15`  
       `pip install tensorflow-gpu==1.15`
6. Command Prompt or else

#### HOW TO RUN
1. Open Command Prompt
2. Move to the directory `cd Neural Network Dependency Parser`
3. Run `python model.py`

#### HOW TO RUN WITH A NEW HYPER PARAMETERS
- You can change manually the hyper parameters in `model.py` from line 19 to line 25 and run `python model.py`
- OR simply you can run this code  
  `python model.py --optimizer=adam --lr=0.001 --activation=relu --hidden=4 --hidden_size=500 -l2_beta=10e-8`   
  Change the parameters as you want (for list of the hyper parameters scroll down in this file)

#### OUTPUT FOLDER
- If you don't want the output arcs of training data, delete the code `output/ud_english-out.txt` in `model.py` line 26  
- If you want, don't forget to change the `ud_english-out.txt` to your output name each time you're running the program  
- See the output arcs of training data in folder output

#### HOW TO CHANGE THE DATASET
- Open `data.py` at line 526
- Change the `ud_english` to your corpus folder name

#### HOW TO ADD A NEW CORPUS/DATASET
- Open corpora folder and copy your new corpus folder inside
- In `data.py` line 70 write the code above :  
  `ud_english = LazyCorpusLoader(`  
  `'ud_english', UniversalDependencyCorpusReader, r'.*\.conll')`  
- Note: change the `ud_english` to your corpus folder name

#### HYPER-PARAMETERS OPTION
- learning rate `--lr`
- number of hidden layers `--hidden`
- hidden layer size `--hidden_size`
- number of epochs `--epochs`
- l2 regularization beta `-l2_beta`
- activation `--activation` can be `relu` or `cube`
- optimizer `--optimizer`, can be `adam` or `adagrad`

#### FINAL RESULT
See the final result documentation in folder `output/final`

- Based on the Paper
  | Dataset    | Test LAS | Test UAS | Dev LAS | Dev UAS | Parsing Speed |
  | :--------: | :------: | :------: | :-----: | :-----: | :-----------: |
  | Arabic     |  73.0    |  78.3    |  73.2   |  78.8   |      71       |
  | Chinese    |  64.6    |  72.8    |  68.5   |  75.3   |      74       |
  | English    |  79.9    |  82.4    |  81.2   |  83.8   |      86       |
  | Indonesian |  73.0    |  78.6    |  71.3   |  77.1   |      87       |
  
- New Hyper-Parameters
  | Dataset    | Test LAS | Test UAS | Dev LAS | Dev UAS | Parsing Speed |
  | :--------: | :------: | :------: | :-----: | :-----: | :-----------: |
  | Arabic     |  73.5    |  78.8    |  73.6   |  79.0   |      79       |
  | Chinese    |  66.5    |  74.9    |  68.7   |  75.6   |      71       |
  | English    |  80.4    |  83.0    |  81.1   |  83.7   |      98       |
  | Indonesian |  74.2    |  79.9    |  72.7   |  78.5   |      83       |
