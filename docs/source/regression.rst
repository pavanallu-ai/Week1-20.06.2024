.. _regression:

Regression
============

Import Statement::

    from regressor import *

.. function:: Linear_Regression( Iteration , Learning_Rate)

   :param Iteration: No. of iterations
   :type Iteration:  int

   :param Learning_Rate: The rate at which the model should learn
   :type Learning_Rate:  float


.. function:: fit( X , Y)

   :param X: the x_train
   :type X: output from sklearn train_test_split()

   :param Y: the y_train
   :type Y: output from sklearn train_test_split() 
