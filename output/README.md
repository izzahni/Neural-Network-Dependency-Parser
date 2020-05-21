##RUNNING EXAMPLE
1. Original based on the paper
   python model.py --optimizer=adam --lr=0.001 --activation=relu --hidden_size=200 -l2_beta=10e-8
   optimizer=adagrad
   lr=0.001
   activation=relu
   hidden=1
   hidden_size=200
   l2_beta=10e-8
2. Based on the paper but using Adam optimizer
   python model.py --optimizer=adam --lr=0.001 --activation=relu --hidden_size=200 -l2_beta=10e-8
   optimizer=adam
   lr=0.001
   activation=relu
   hidden=1
   hidden_size=200
   l2_beta=10e-8
3. Create a new hyper-parameters
   python model.py --optimizer=adam --lr=0.001 --activation=relu --hidden=4 --hidden_size=500 -l2_beta=10e-8
   optimizer=adam
   lr=0.001
   activation=relu
   hidden=4
   hidden_size=500
   l2_beta=10e-8