# Fraud Detection

The idea and data of this project comes from ZINDI:
[Fraud Detection in Electricity and Gas Consumption Challenge](https://zindi.africa/competitions/fraud-detection-in-electricity-and-gas-consumption-challenge/data)

Collaborators: [@BasaJess](https://github.com/BasaJess), [@Kathixx](https://github.com/Kathixx) and [@MaJo632](https://github.com/MaJo632)

The short-term (4 days) project was part of the Datascience & AI Bootcamp from [@neuefische](https://github.com/neuefische).

## About Fraud Detection

Fraud detection is essential to protect individuals, businesses, and institutions from financial loss, reputational damage, and security breaches. As digital transactions and online services grow, so do opportunities for fraudsters to exploit vulnerabilities. Traditional rule-based systems often fail to keep up with evolving fraud tactics.

Machine learning offers a powerful solution by learning patterns from vast amounts of data and adapting to new threats in real time. It can detect subtle anomalies, uncover hidden relationships, and flag suspicious activities more accurately and efficiently than manual methods. By continuously improving with new data, machine learning helps stay one step ahead of increasingly sophisticated fraud schemes.

## Progress

**Data:**
Zindi provides data from The Tunisian Company of Electricity and Gas (STEG). It contains two different files:

- client data: such as district, region, creation and the target value (fraud or not)
- billing history from 2005 -2019: e.g. invoice date, tarif type, counter code, consommation level

**Feature Engineering:**
The big challenge in this project was feature engineering. Due to the short timeframe of this project, we decided to continue modelling after two days of cleaning and understanding the data and feature engineering, even though we know we could have done much more to optimise our results.

**Imbalanced Data:**
Another typical problem with fraud detection is an imbalanced dataset - as it was here. So we tried different under- and oversampling methods (like SMOTE) to face this issue.

**Modelling:**
We started to model different classification models: Logistic regression, K-nearest Neighbors, Decision Tree and SGD-Classifier.
Our baseline model was a decision tree withoud GridSearch.
To optimize our models, we also implemented XGBoost, Random Forest and Stacking.

## Results

Surprisingly, our baseline model (decision tree) performed best. Even advanced (ensemble) methods such as XGBoost, Random Forest or Stacking couldn't produce a better result.

| Model                         | ROC AUC Score |
| ----------------------------- | ------------- |
| baseline model: decision tree | 0.76          |
| random forest                 | 0.62          |
| stacking                      | 0.62          |
| XGBoost                       | 0.62          |

## Repo Structure

- 0_data: data available from Zindi
- 1_eda: explorative data analysis and feature engineering
- 2_models: different implemented simple and advanced models
- 3_visualization: plots of imbalanced data and result
- 4_additional: additional files, which where not used in the final presentation but may be useful, e. g. previous feature engineering notebooks

## Set up your Environment

### **`macOS`** type the following commands :

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
