import numpy as np
import tensorflow as tf

coefficients = np.array([[1.], [-20.], [100.]])

# start up tensorflow
w = tf.Variable(0, dtype=tf.float32)        # startup parameter, minimize a fixed function of w
x = tf.placeholder(tf.float32, [3,1])        # minimize a training data
# placeholder: x is the something you provide value for in future
# cost = w**2 - 10*w + 25
cost = x[0][0]*w**2 + x[1][0]*w + x[2][0]
# cost = tf.add(tf.add(w**2, tf.multiply(-10., w)),25)        #
train = tf.train.GradientDescentOptimizer(0.01).minimize(cost)  # learning rate 0.01, goal is to minimize "cost"

# idiomatic
init = tf.global_variables_initializer()    #
session = tf.Session()                      #
session.run(init)                           # initialize global variable
print(session.run(w))                       # run the learning algorithm

session.run(train, feed_dict={x:coefficients})                          # run 1 session of gradient descent
print(session.run(w))                       #

for i in range(1000):
    session.run(train, feed_dict={x:coefficients})
print(session.run(w))
