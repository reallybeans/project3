# Coworking Space Service Extension
The Coworking Space Service is a set of APIs that enables users to request one-time tokens and administrators to authorize access to a coworking space. This service follows a microservice pattern and the APIs are split into distinct services that can be deployed and managed independently of one another.

For this project, you are a DevOps engineer who will be collaborating with a team that is building an API for business analysts. The API provides business analysts basic analytics data on user activity in the service. The application they provide you functions as expected locally and you are expected to help build a pipeline to deploy it in Kubernetes.

## Getting Started

### Dependencies
#### Local Environment
1. Python Environment - run Python 3.6+ applications and install Python dependencies via `pip`
2. Docker CLI - build and run Docker images locally
3. `kubectl` - run commands against a Kubernetes cluster
4. `helm` - apply Helm Charts to a Kubernetes cluster

#### Remote Resources
1. AWS CodeBuild - build Docker images remotely
2. AWS ECR - host Docker images
3. Kubernetes Environment with AWS EKS - run applications in k8s
4. AWS CloudWatch - monitor activity and logs in EKS
5. GitHub - pull and clone code

#### Project Structure
```shell

├── CODEOWNERS
├── LICENSE.txt
├── README.md
├── analytics
│   ├── Dockerfile
│   ├── __init__.py
│   ├── app.py
│   ├── config.py
│   └── requirements.txt
├── db
│   ├── 1_create_tables.sql
│   ├── 2_seed_users.sql
│   └── 3_seed_tokens.sql
├── deployment
│   ├── configmap.yaml
│   ├── coworking.yaml
│   └── secret.yaml
├── deployment-local
│   ├── configmap.yaml
│   └── coworking.yaml
├── buildspec.yml
└── screenshots
    ├── CloudWatchCluster.png
    ├── CloudWatchClusterLogs.png
    ├── codeBuild.png
    ├── codeBuildLogs.png
    ├── CurlReportDaily.png
    ├── describe_svc_postgresql-service.png
    ├── DescribeDeploymentCoworking.png
    ├── DescribeDeploymentPostgresql.png
    ├── DockerImage.png
    ├── GetPods.png
    ├── GetService.png
    ├── get_deployment.png
    └── logs.png
    
- `scripts`: Bash scripts to facilitate project tasks.
- `db`: SQL scripts for seeding data.
- `deployment`: Kubernetes YAML files for deployment and configuration.
    
    
### CloudWatch Metrics in EKS

Refer to [CloudWatch Metrics in EKS](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Observability-EKS-addon.html) for more information on CloudWatch metrics in EKS.
    
### CloudWatch

View metrics and logs in CloudWatch:

![CloudWatch](./screenshots/CloudWatchCluster.png)

### Get Web API URL

To access the Web API, follow these steps:

1. Get the load balancer external IP:

   ```shell
   kubectl get svc 
   
   ![Kubectl Get SVC](./screenshots/GetService.png)

2. Access the Web API using the provided external IP.

   ![Web API](./screenshots/CurlReportDaily.png) 
