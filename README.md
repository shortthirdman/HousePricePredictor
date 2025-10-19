# HousePricePredictor

House price prediction using Regression with Streamlit and FastAPI

---

## Local Development Setup

```shell
python src/data/run_processing.py --input data/raw/house_data.csv --output data/processed/cleaned_house_data.csv

python src/features/engineer.py --input data/processed/cleaned_house_data.csv --output data/processed/featured_house_data.csv --preprocessor models/trained/preprocessor.pkl

python src/models/train_model.py --config configs/model_config.yaml --data data/processed/featured_house_data.csv --models-dir models --mlflow-tracking-uri http://localhost:5555
```

```shell
docker compose build

docker image ls

docker compose up -d

docker compose ps #Need to run from root directory
```

---

## Download Datasets

```python
import kagglehub

# Download latest version
path = kagglehub.dataset_download("yasserh/housing-prices-dataset")

print("Path to dataset files:", path)
```

```shell
#!/bin/bash

#!/bin/bash
curl -L -o ~/Downloads/housing-prices-dataset.zip 'https://www.kaggle.com/api/v1/datasets/download/yasserh/housing-prices-dataset'
```

---

## Kaggle Datasets

- [yasserh/housing-prices-dataset](https://www.kaggle.com/datasets/yasserh/housing-prices-dataset)

- [sukhmandeepsinghbrar/housing-price-dataset](https://www.kaggle.com/datasets/sukhmandeepsinghbrar/housing-price-dataset)

- [House Prices - Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)


## CI/CD

```shell
eksctl create cluster -f eks-cluster-config.yaml

aws eks update-kubeconfig --region us-east-1 --name my-cluster

kubectl get nodes

kubectl apply -f manifest.yaml

kubectl edit configmap aws-auth -n kube-system

kubectl apply -f deploy-cluster-role.yaml

kubectl apply -f bind-github-oidc.yaml
```