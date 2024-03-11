# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the required library and read the dataframe.
2. Write a function computeCost to generate the cost function.
3. Perform iterations og gradient steps with learning rate.
4. Plot the Cost function using Gradient Descent and generate the required graph.


## Program:
```
/*
Program to implement the linear regression using gradient descent.
Developed by: KEERTHI VASAN A
RegisterNumber:  212222240048
*/
```
```PY
import numpy as np
import pandas as pd
from sklearn.preprocessing import StandardScaler
def linear_regression(X1,y,learning_rate=0.1,num_iters=1000):
    X = np.c_[np.ones(len(X1)),X1]
    theta = np.zeros(X.shape[1]).reshape(-1,1)
    for _ in range(num_iters):
        predictions = (X).dot(theta).reshape(-1,1)
        errors=(predictions-y).reshape(-1,1)
        theta-=learning_rate*(1/len(X1))*X.T.dot(errors)
    return theta
data=pd.read_csv("/content/50_Startups.csv")
data.head()
X = (data.iloc[1:,:-2].values)
X1 =X.astype(float)
scaler = StandardScaler()
y = (data.iloc[1:,-1].values).reshape(-1,1)
X1_Scaled = scaler.fit_transform(X1)
Y1_Scaled = scaler.fit_transform(y)
print(X)
print(X1_Scaled)
theta=linear_regression(X1_Scaled,Y1_Scaled)
new_data=np.array([165349.2,136897.8,471784.1]).reshape(-1,1)
new_Scaled=scaler.fit_transform(new_data)
prediction=np.dot(np.append(1,new_Scaled),theta)
prediction= prediction.reshape(-1,1)
pre = scaler.inverse_transform(prediction)
print(prediction)
print(f"Predicted value:{pre}")
```

## Output:

![1](https://github.com/VARSHINI22009118/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119401150/48a477c7-c5a9-4ff3-946a-1cb08a30ed3f)
![2](https://github.com/VARSHINI22009118/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119401150/2183a3df-f122-46d4-bd31-45085e3b560a)
![3](https://github.com/VARSHINI22009118/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119401150/f528b30f-2408-4b8f-ab53-568a64f54e7a)
![4](https://github.com/VARSHINI22009118/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119401150/b8b34d95-274e-4703-8fc1-13e3afd98971)
![5](https://github.com/VARSHINI22009118/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119401150/2f22e471-c3bc-4139-8feb-dd3a89aa26a6)
![6](https://github.com/VARSHINI22009118/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/119401150/f654cb18-ef63-470c-8177-a58d06ed87ad)



## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
