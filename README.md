# Grab AI challenges - Traffic Management

## Prerequisites
This solution is built with [Surprise Python](http://surpriselib.com/) packages ,[Pandas Python](https://pandas.pydata.org/) and [Jupyter Notebook](https://jupyter.org/).

### Installation for Surprise Python via PyPI
```
pip install surprise
```
You'll need Python 3.6 at least and [Microsoft Visual C++ 14.0](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) installed. Please refer this [tutorial](https://www.scivision.dev/python-windows-visual-c-14-required/) to install the Microsoft Visual C++ 14.0.

### Installation for Pandas Python via PyPI
```
pip install pandas
```
You'll need Python 3.6 at least.

## Before code execution
As the GitHub's file size limitation, the model is zipped as model_file_v2.zip. Please unzip the model file and place it together with the notebook file.

## Load the Test data
Use Jupyter Notebook to open the provided notebook file (Evaluate_Model.ipynb).
You need to modify the file path in the first cell of the notebook before executing the code.
```
test_file_path = "path/to/test_file"
```

## Running the code
Execute the cells in the notebook.


## Model Evaluation
RMSE will be calculated by using the function provided by the package.
```
from surprise import accuracy
accuracy.rmse(prediction)
```

### Single prediction
In order to predict the particular location with the specify time information, the following code will able to predict the demand by using the given information.
```
geohash = "qp0d45" #string datatype
day = 47 # integer datatype
time = "8:45" # string datatype

uid = geohash
iid = str(day) + " " + time

pred = model.predict(uid, iid)
pred.est
```
