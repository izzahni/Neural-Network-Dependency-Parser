## NEURAL NETWORK DEPENDENCY PARSER
A Neural Network Dependency Parser using TensorFlow based on paper [A Fast and Accurate Dependency Parser using Neural Networks]  
Inspired by https://github.com/bryanlimy/neural-dependency-parser  

### HOW TO RUN
1. Open command prompt or else
2. Move to your folder directory, example: 'cd Documents\Neural Network Dependency Parser'
3. Run 'python model.py'

### HOW TO RUN USING MY OWN HYPER PARAMETERS
1. You can change manually the hyper parameters in model.py from line 19 to line 25 and run 'python model.py'
2. OR simply you can run 'python model.py --optimizer=adam --lr=0.001 --activation=relu --hidden=4 --hidden_size=500 -l2_beta=10e-8'  
   Change the parameters as you want (for list of the hyper parameters scroll down in this file).

### OUTPUT FOLDER
Note: If you don't want the output arcs of the training data, delete the code "output/ud_english-out.txt" in model.py line 26  
      If you want, don't forget to change the "ud_english-out.txt" to your output name everytime you running the program.

### HOW TO CHANGE THE DATASET
- Open data.py at line 526
- Look at the "data_set=ud_english" and change the "ud_english" to your corpus folder name

### HOW TO ADD A NEW CORPUS/DATASET
- Open corpora folder and copy your new corpus folder inside
- In data.py line 70 write the code above :  
  ud_english = LazyCorpusLoader(  
  'ud_english', UniversalDependencyCorpusReader, r'.*\.conll')  
- Note: change the "ud_english" to your corpus folder name

### HYPER-PARAMETERS OPTION
- learning rate `--lr`
- number of hidden layers `--hidden`
- hidden layer size `--hidden_size`
- number of epochs `--epochs`
- l2 regularization beta `-l2_beta`
- activation `--activation` can be `relu` or `cube`
- optimizer `--optimizer`, can be `adam` or `adagrad`
