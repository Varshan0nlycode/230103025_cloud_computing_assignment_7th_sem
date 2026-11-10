# CS4032 Cloud Computing Project

## Project Title
**Knowledge Distillation and Cloud Deployment of a Lightweight Language Model for Command Parsing**

## Repository
[GitHub Repository](https://github.com/Varshan0nlycode/230103025_cloud_computing_assignment_7th_sem)

## Project Overview
This project focuses on developing a compact language model capable of understanding and extracting structured information from user commands. Knowledge distillation is used to transfer command-parsing capabilities from the larger Phi-3.5 teacher model to the smaller Pythia-70M student model.

The trained student model is integrated into a FastAPI-based application and deployed on Kubernetes using k3d. The project also incorporates automated CI pipelines, deployment verification, and performance benchmarking.

## System Architecture
The overall workflow consists of the following stages:

Command Dataset → Teacher Model Annotation → Data Preprocessing → Student Model Fine-Tuning → Model Evaluation → FastAPI Integration → Docker Containerization → Kubernetes Deployment

## Model Training Details
- **Teacher Model:** Phi-3.5
- **Student Model:** EleutherAI/Pythia-70M
- **Training Dataset:** 1,500 samples
- **Training Duration:** 3 epochs
- **Evaluation Dataset:** 100 samples
- **Training Platform:** Google Colab with NVIDIA T4 GPU

## Model Evaluation

The performance of two student model versions was assessed using multiple evaluation parameters.

| Evaluation Metric | Version 1 | Version 2 |
|---|---:|---:|
| JSON Format Validity | 100% | 100% |
| Intent Recognition Accuracy | 83% | 79% |
| Date Extraction Accuracy | 80% | 80% |
| Time Extraction Accuracy | 80% | 85% |
| Location Extraction Accuracy | 79% | 79% |
| Complete Frame Accuracy | 40% | 39% |

## Performance Benchmarking
Locust was used to measure the application's response time and handling capacity under concurrent requests.

The test configuration and observations were as follows:

- **Concurrent Users:** 4
- **Test Duration:** 2 minutes
- **Total Requests:** 365
- **Failed Requests:** 0
- **Median Response Time:** 1,300 ms
- **95th Percentile Latency:** 2,900 ms
- **Request Throughput:** 3.07 requests per second

## Model Artifacts
The fine-tuned model files and their corresponding checksum information are available in the GitHub release named `model-v1`. These artifacts allow the trained model to be retrieved and verified independently.

## Application Deployment
The project uses GitHub Actions to automate application testing and Kubernetes deployment.

The `test-kubernetes.yml` workflow is responsible for:
- Building the application Docker image.
- Initializing a Kubernetes cluster through k3d.
- Deploying the application.
- Running deployment and cluster health checks.
- Removing the cluster after testing.

The `ci.yml` workflow automates:
- Code quality checks and linting.
- FastAPI unit testing.
- Model performance evaluation.
- Quality threshold verification.
- Secret and credential scanning.

The deployed API provides three primary endpoints:

- `/parse` – Processes user commands and generates structured JSON output.
- `/healthz` – Checks the application's health status.
- `/readyz` – Determines whether the application is ready to receive requests.

## Testing and Verification
Several testing procedures have been incorporated to verify the reliability of the application and its deployment infrastructure.

These include:
- Unit testing of FastAPI endpoints.
- Verification of Kubernetes deployments.
- Testing of rolling updates and rollback procedures.
- Recovery testing after pod failures.
- Load distribution and balancing verification.
- Performance assessment using Locust.
- Model quality evaluation with a minimum JSON validity threshold of 95%.
- Network subnet allocation and Network Access Control List (NACL) simulation.

## Cloud Networking
The project also includes basic cloud networking configurations and simulations. Subnet definitions and NACL rules are maintained in the following files:

- `network/subnets.md`
- `network/nacl.json`

These configurations demonstrate subnet planning and network traffic access control.

## Experimental Results
Additional evaluation outputs, performance measurements, and experimental observations are stored in the repository's `results/` directory.

## Limitations and Future Improvements
Despite successfully implementing the core model training and deployment workflow, certain limitations remain:

- Model fine-tuning was conducted on Google Colab rather than directly on local computing infrastructure.
- Kubernetes deployment experiments were executed on GitHub Actions runners instead of the local Mac environment.
- Integration with cloud object storage has not yet been completed.
- Some of the planned deployment experiments remain unfinished.
- Although individual field extraction performs reasonably well, the model achieves relatively lower accuracy when all extracted fields must be correct simultaneously.
# 230103025_cloud_computing_assignment_7th_sem_
