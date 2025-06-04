[![Shipping files](https://github.com/neuefische/ds-ml-project-template/actions/workflows/workflow-02.yml/badge.svg?branch=main&event=workflow_dispatch)](https://github.com/neuefische/ds-ml-project-template/actions/workflows/workflow-02.yml)

# ML Project: Fraud Detection in Electricity and Gas Consumption

## About the project

This repository solves Zindi’s “Fraud Detection in Electricity and Gas Consumption” challenge. The aim is to detect fraudulent electricity / gas usage patterns using historical consumption and customer data.

The data used for this is: [fraud detection dataset](https://zindi.africa/competitions/instadeep-fraud-detection-in-electricity-and-gas-consumption-challenge/data).

---

Utility companies lose revenue when customers manipulate their meter readings. The challenge was to build a model that predicts whether a reading is fraudulent (1) or legitimate (0).

## Dataset
The dataset contains the following files:

### train.zip
Client_train.csv - Client information in the train population
Invoice_train.csv - Clients invoice in the train set

### test.zip
Client_test.csv - Client information for the test population
Invoice_test.csv - Clients invoice in the test set

SampleSubmission.csv - example of the submission file

### Columns

Client Data

| Variable       | Description                  |
| -------------- | ---------------------------- |
| Client\_id     | Unique id for client         |
| District       | District where the client is |
| Client\_catg   | Category client belongs to   |
| Region         | Area where the client is     |
| Creation\_date | Date client joined           |
| Target         | fraud: 1, not fraud: 0       |

Invoice Data

| Variable               | Description                                                                                                                                |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Client\_id             | Unique id for the client                                                                                                                   |
| Invoice\_date          | Date of the invoice                                                                                                                        |
| Tarif\_type            | Type of tax                                                                                                                                |
| Counter\_number        | Counter number                                                                                                                             |
| Counter\_statue        | Takes up to 5 values such as working fine, not working, on hold status, etc.                                                               |
| Counter\_code          | Counter code                                                                                                                               |
| Reading\_remarque      | Notes that the STEG agent takes during his visit to the client (e.g., if the counter shows something wrong, the agent gives a “bad” score) |
| Counter\_coefficient   | An additional coefficient to be added when standard consumption is exceeded                                                                |
| Consommation\_level\_1 | Consumption\_level\_1                                                                                                                      |
| Consommation\_level\_2 | Consumption\_level\_2                                                                                                                      |
| Consommation\_level\_3 | Consumption\_level\_3                                                                                                                      |
| Consommation\_level\_4 | Consumption\_level\_4                                                                                                                      |
| Old\_index             | Old index (previous meter reading)                                                                                                         |
| New\_index             | New index (current meter reading)                                                                                                          |
| Months\_number         | Month number                                                                                                                               |
| Counter\_type          | Type of counter                                                                                                                            |


## Set up your Environment



### **`macOS`** type the following commands : 

- For installing the virtual environment you can either use the [Makefile](Makefile) and run `make setup` or install it manually with the following commands:

     ```BASH
    make setup
    ```
    After that active your environment by following commands:
    ```BASH
    source .venv/bin/activate
    ```
Or ....
- Install the virtual environment and the required packages by following commands:

    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/bin/activate
    pip install --upgrade pip
    pip install -r requirements.txt
    ```
    
### **`WindowsOS`** type the following commands :

- Install the virtual environment and the required packages by following commands.

   For `PowerShell` CLI :

    ```PowerShell
    pyenv local 3.11.3
    python -m venv .venv
    .venv\Scripts\Activate.ps1
    python -m pip install --upgrade pip
    pip install -r requirements.txt
    ```

    For `Git-bash` CLI :
  
    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/Scripts/activate
    python -m pip install --upgrade pip
    pip install -r requirements.txt
    ```

    **`Note:`**
    If you encounter an error when trying to run `pip install --upgrade pip`, try using the following command:
    ```Bash
    python.exe -m pip install --upgrade pip
    ```


   
## Usage

In order to train the model and store test data in the data folder and the model in models run:

**`Note`**: Make sure your environment is activated.

```bash
python example_files/train.py  
```

In order to test that predict works on a test set you created run:

```bash
python example_files/predict.py models/linear_regression_model.sav data/X_test.csv data/y_test.csv
```



