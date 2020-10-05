# Subtractor

https://nbviewer.jupyter.org/github/ElmoLee822/Subtractor/blob/master/notebook.ipynb

### Method
Using LSTM to implement the subtractor. Because RNN has a good effect on processing sequential data. \However, RNN will gradually reduce the weight of long-term information with the process of transmission, and LSTM can handle such problems by capturing long-term time correlation.

### Parameters
By adjusting the parameters of Generating data size, training data size, Validation data size, hidden size, batch size. We can observe the result changes and under what parameters the performance is better.

### Results
The results are obtained using the best parameters obtained through experiments.
training data = 63000, validation data = 7000, testing data = 30000, batch size = 64, hidden size = 256
#### ---- MSG accuracy = 0.997767
![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/result_MSG.PNG)

### Experiments
### Experiment-1
#### change training, validation, testing data size, training epoch
Fixed HIDDEN_SIZE = 128, BATCH_SIZE = 128, the data size of the first and second groups is 80,000, the data size of the 3rd, 4th, and 5th groups is 100000, in the 4th group training data = 63000, validation data = 7000, The best performance is when testing data = 30000. In the fifth group, because the size of the training data increased, the effect of training became bad and the accuracy also became bad.

![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/experiment-1_grid.PNG)
![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/experiment-1.PNG)

#### Group4 model accuracy and loss
![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/group-4.PNG)

### Experiment-2
#### Tune batch size
Training data size = 63000, Validation data size = 7000, Testing data size = 30000, training epoch = 80, hidden size = 128
1. batch size = 64
2. batch size = 128
3. batch size = 256
The batch size is 64, the performace is higher than the other two, and it tends to converge faster, and the loss also drops faster

#### accuracy in different batch size
![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/tune_batch_size.PNG)

#### --- MSG prediction result
![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/batch_MSG_result.PNG)

### Experiment - 3
#### Tune hidden size
Training data size = 63000, Validation data size = 7000, Testing data size = 30000, training epoch = 80, batch size = 128
1. hidden size = 64
2. hidden size = 128
3. hidden size = 256
A larger hidden size tends to converge faster, and the loss will drop faster.
#### accuracy in different hidden size
![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/tune_hidden_size.PNG)

#### --- MSG prediction result
![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/hidden_MSG_result.PNG)

#### Combine adder and subtractor together
label length = 13 [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, +, -, ‘’],
Training data size = 99000, Validation data size = 11000, Testing data size = 90000, Epoch = 35, batch size = 128, hidden size = 128

Using this method to combine the adder and the subtractor to make the result is not bad, MSG prediction is about 0.93678

![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/adder_subtractor_MSG.PNG)

![image](https://github.com/ElmoLee822/Subtractor/blob/master/img/adder_subtractor_result.PNG)


