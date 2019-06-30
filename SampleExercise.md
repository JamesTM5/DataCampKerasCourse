Sample Exercise
======

Learning Objectives Addressed
======
  * LO1. (partial) The Learner can identify and employ common deep learning
   techniques in a variety of contexts.
  * LO2.1. (partial) The learner can use Keras to build sequential models, convolutional and recurrent neural networks.
  * LO2.1.2. The Learner will be able to `model.add` the input, output and
   hidden layers and define dimensionality appropriately and visualise them
   using `model.summary()`.

Context
======

Your company has data from an app with which users can calorie count.  The data
you have are sociodemographic (age, gender and ethnicity) and self-reported food
 intake over time.  You need to predict which food to market at a given member
 of the population.

Having addressed the variable length issue with the data caused by users’
relatively short term use of the app, This data are now stored in two numpy
 arrays such as you prepared in the previous task: one called data_train (for
 training data) and one called data_test (for test data).  You can inspect these
 as you wish, working with the sequential API to complete the task.

Code
======
```from keras.models import Sequential
from keras.layers import Dense
model = Sequential()

# add an input layer suitable for our data and a fully connected hidden layer of
# 20 neurons (use a 'relu' activation)
model.___

# add an output layer
model.___

# inspect the model structure
print(model.___

# identify the number of parameters your network has in its input and
# hidden layers.
num_parameters = ___
```
Solution
======
```from keras.models import Sequential
from keras.layers import Dense
model = Sequential()

# add a dense hidden layer with 20 neurons accepting five inputs (age, gender,
#  ethnicity, food_name and when_eaten)
model.add(Dense(20, input_shape=(5,), activation="relu"))

# add an output layer constrained to a single number corresponding to an item
# from food_name
model.add(Dense(1))

print(model.summary())

# num_parameters is the sum of the connections between each input and each
# neuron (20*5) plus the bias weights of the neurons (20)
num_parameters = 170
```
