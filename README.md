# Insurance MLOps Project

This project implements an end-to-end MLOps workflow to predict whether a customer is likely to purchase additional insurance. It includes data processing, model training, a web prediction service, containerization with Docker, and deployment on Google Kubernetes Engine (GKE) on Google Cloud Platform .

---

## 1. Project Structure

- `pipeline.py` – End-to-end ML pipeline (ingest, clean, train, evaluate, log).
- `steps/` – ML steps:
  - `ingest.py` (load data)
  - `clean.py` (preprocessing)
  - `train.py` (training pipeline)
  - `predict.py` (evaluation utilities)
- `models/` – Trained model (`model.pkl`).
- `app.py` – Flask web application exposing the prediction endpoint.
- `templates/` – HTML templates (`index.html`, `result.html`) for the UI.
- `tests/` – Unit tests for ingestion and cleaning.
- `config.yml` – Configuration for data paths and model hyperparameters.
- `Dockerfile` – Docker image definition for the web service.
- `deployment.yaml` / `service.yaml` – Kubernetes manifests for GKE deployment.
- `.github/workflows/cicd.yaml` – CI/CD pipeline (build, push image, deploy) [web:49][web:52].

---

## 2. Local Setup

```bash
git clone https://github.com/Yassinekacem/mlops-insurance-cicd-docker-k8s-.git
cd mlops-insurance-cicd-docker-k8s-

python3 -m venv venv
# Windows
venv\Scripts\activate
# Linux / macOS
source venv/bin/activate

pip install --upgrade pip
pip install -r requirements.txt


