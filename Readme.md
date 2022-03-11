# MLflow Tutorial with Azure ML backend

MLflow requires backend server for recording tracks or storing artifacts. Currently, MLflow client can interface with a variety of backends, such as, local file path, http server, database, or [databricks workspace](https://tsmatz.github.io/azure-databricks-exercise/exercise10-mlflow.html).<br>
Azure Machine Learning (shortly, Azure ML or AML) can also integrate with MLflow, and will become one of such backend's service.

In this repository, I'll show you MLflow through ML lifecycle, with Azure Machine Learning backend.

1. [Track logs and metrics](./01_track_logs.ipynb)
2. [Compare models](./02_compare_models.ipynb)
3. [Train MLflow project](./03_run_mlflow_project.ipynb)
4. [Model management and deployment](./04_model_deploy.ipynb)

See [official document](https://docs.microsoft.com/en-us/azure/machine-learning/concept-mlflow#compare-mlflow-and-azure-machine-learning-clients) for MLflow-AML integration's coverage.

## Installing and Setup

- Create new "Machine Learning" resource in [Azure Portal](https://portal.azure.com/) .

- For working client, create Ubuntu Server 20.04 LTS virtual machine resource in [Azure Portal](https://portal.azure.com/) and set up as follows.

```
# Make sure that Python is installed
python3 -V

# Install pip
sudo apt-get update
sudo apt-get install -y python3-pip
sudo -H pip3 install --upgrade pip

# Install Jupyter
pip3 install jupyter

# Install mlflow packages
pip3 install mlflow==1.23.0
pip3 install azureml-mlflow==1.39.0

# Install required packages in this tutorial
pip3 install numpy scikit-learn matplotlib
````

> Note : The ```azureml-mlflow``` installation automatically brings ```azureml-core``` (Azure ML Python SDK core library).

- Clone this repository.

```
git clone https://github.com/tsmatz/mlflow-azureml
```

- Start Jupyter notebook as follows.<br>
  This will show the access url in console, such as ```http://localhost:8888/tree?token=xxxxxxxxxx```.<br>
  (The default port is 8888.)

```
jupyter notebook
```

- Connect to Ubuntu server with SSH tunnel (port forwarding) from your working desktop in order to access notebook URL.<br>
  For instance, the following is the SSH tunnel setting on "PuTTY" terminal client in Windows. (You can use ```ssh -L``` option in Mac OS.)<br>
  ![SSH Tunnel settings with putty](https://tsmatz.github.io/images/github/azure-ml-tensorflow-complete-sample/20191225_SSH_Tunnel.jpg)

- Copy the notebook URL (```http://localhost:8888/?token=...```) and open this address with your web browser.

*Tsuyoshi Matsuzaki @ Microsoft*
