# Developing a Neural Network Classification Model

## AIM
To develop a neural network classification model for the given dataset.

## THEORY
The Iris dataset consists of 150 samples from three species of iris flowers (Iris setosa, Iris versicolor, and Iris virginica). Each sample has four features: sepal length, sepal width, petal length, and petal width. The goal is to build a neural network model that can classify a given iris flower into one of these three species based on the provided features.

## Neural Network Model
<img width="577" height="826" alt="WhatsApp Image 2026-04-27 at 2 20 03 PM" src="https://github.com/user-attachments/assets/a29d90b2-3110-4238-8d22-9e56eca01b77" />


## DESIGN STEPS
### STEP 1: Import Required Libraries

Import necessary Python libraries such as:

numpy, pandas for data handling
sklearn for dataset and preprocessing
torch (PyTorch) for building the neural network



### STEP 2: 
Load the Iris dataset using sklearn.datasets.


### STEP 3: 
Split dataset into training and testing sets.Normalize/standardize the input features.Convert data into tensors (for PyTorch)


### STEP 4:Define the Neural Network Model
Create a neural network class using nn.Module 

### STEP 5: Train the Model
Perform training using:

Forward pass
Loss calculation
Backpropagation
Weight update


### STEP 6:  Evaluate the Model
Test the model using test dataset
Calculate accuracy
Check how well the model classifies iris species





## PROGRAM

### Name:JAWAHAR BABU S

### Register Number:212224220041

```python
class PeopleClassifier(nn.Module):
    def __init__(self, input_size):
        super(PeopleClassifier, self).__init__()
        self.fc1 = nn.Linear(input_size, 32)
        self.fc2 = nn.Linear(32, 16)
        self.fc3 = nn.Linear(16, 8)
        self.fc4 = nn.Linear(8, 4)
       




    def forward(self, x):
      x = F.relu(self.fc1(x))
      x = F.relu(self.fc2(x))
      x = F.relu(self.fc3(x))
      x = self.fc4(x)
      return x



# Initialize the Model, Loss Function, and Optimizer

def train_model(model, train_loader, criterion, optimizer, epochs):
  for epoch in range(epochs):
    for inputs,lables in train_loader:
      optimizer.zero_grad()
      output=model(inputs)
      loss=crterion(outputs,labels)
      loss.backward()
      optimizer.step()





    if (epoch + 1) % 10 == 0:
        print(f'Epoch [{epoch+1}/{epochs}], Loss: {loss.item():.4f}')

```

### Dataset Information
<img width="1511" height="345" alt="image" src="https://github.com/user-attachments/assets/c11a7cca-ee2d-4684-b721-f9343612bf0d" />


### OUTPUT
<img width="1183" height="761" alt="WhatsApp Image 2026-04-27 at 2 22 11 PM (1)" src="https://github.com/user-attachments/assets/bfef18e7-5aa9-4356-9219-9a02542632f7" />

## Confusion Matrix


<img width="807" height="597" alt="WhatsApp Image 2026-04-27 at 2 20 20 PM" src="https://github.com/user-attachments/assets/6436c100-6841-4078-8c88-715a3ccf469c" />



## Classification Report
<img width="1183" height="761" alt="WhatsApp Image 2026-04-27 at 2 22 11 PM (1)" src="https://github.com/user-attachments/assets/bfef18e7-5aa9-4356-9219-9a02542632f7" />


### New Sample Data Prediction
<img width="1430" height="376" alt="image" src="https://github.com/user-attachments/assets/90554f70-f884-46d5-924e-9994a4120b33" />

## RESULT
Thus, the neural network model correctly predicts the class of iris flowers, fulfilling the objective of the experiment.
