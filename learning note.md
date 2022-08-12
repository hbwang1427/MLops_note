# MLops

## MLops vs Devops

DevOps is a contraction of Development (Dev) and Operations (Ops). It combines two essential functions of the IT department: application development and systems engineering.  DevOps tries to shorten development cycles—and accelerate the velocity of output for software engineering teams. It does so by introducing automation, updated processes, and working methods for development teams. More broadly, DevOps brings in two principles to the software development process:

Given the unique nature of machine learning, here are some practical ways MLOps differs from DevOps: 

Continuous Integration is extended from testing and validating code, to also testing and validating models and data

Continuous Delivery is extended from automating steps to delivering applications into production to automatically delivering data pipelines that trigger a machine learning prediction

Continous Training is introduced—which is unique to machine learning—where models are automatically retrained for deployment

Continuous Monitoring is introduced—which monitors production data breaks in quality, model performance, and business metrics tied to the machine learning model


## Reimagining the data science workflow for MLOps

Given the additional complexity of deploying machine learning models into production—how can data teams start adopting MLOps into their data science workflows? In this section, we introduce a simplified step-by-step approach in an MLOps process:   

- Building: Once models are created, they are typically placed in an auditable repository under version control to support reuse across the enterprise.

- Evaluation: The model predictions' quality is quantified at this stage by measuring the newly trained model performance on a new and independent dataset.

- Productionizing: Export, deploy, and integrate the model or pipeline into production systems and applications.

- Testing: continuous testing is important for ML-based applications, which is concerned with automatically retraining and serving the models.

- Deployment: Continuous monitoring is required to ensure optimal performance. The model can be retrained or replaced with a new model as data changes.

- Monitoring and observability: Many companies face challenges when it comes to moving machine learning models into production environments.

## MLops tools

- Kubeflow: Kubeflow is a suite of tools for running Machine Learning workflows on Kubernetes clusters. The goal of Kubeflow is to enable the best open-source machine learning solutions to run on a Kubernetes cluster in a simple, portable, and scalable way. Originally Kubeflow was the open-source implementation of TensorFlow Extended (TFX), which is an end-to-end platform for deploying machine learning pipelines in production. Kubeflow thus allowed to simplify the execution of TensorFlow jobs on KubernetesMLFlow

- MLflow is a tool for industrializing the end-to-end development process of Machine Learning projects. Its ambition is to simplify the development of Machine Learning projects in companies by facilitating models' monitoring, reproduction, management, and deployment.

- Data Version Control (DVC): DVC (Data Version Control) is a Python package that makes managing your data science projects easier. This tool is an extension of Git for Machine Learning, as stated by its main contributor Dmitry Petrov in this presentation. DVC is both comparable and complementary to Git.

- Pachyderm: Pachyderm is a version control tool for machine learning and data science like DVC. On top of that, it is based on Docker and Kubernetes, which helps it run and deploy Machine Learning projects on any cloud platform. In addition, pachyderm ensures that all data ingested into a machine learning model is versioned and traceable.

* 数据管理：使用了 DVC 进行数据版本管理，当然也可以选择 Pachyderm，Hudi 等更大型的框架。
* 特征管理：目前还没有实现。这方面开源框架的选择主要是 Feast 和 Hopsworks。
* 流程编排：我们选择了比较好上手的 Prefect 来进行各种流程的编排，这里可以选的就有很多了，从老牌的 Luigi，Airflow 到新一代的 Flyte，Kubeflow 等。
* 实验记录：选用了目前最流行的 MLFlow，主要也是因为可以自行部署。其它像 Weights and Biases，Neptune，谷歌的 MLMD 等也都是不错的选择。
* 参数管理：选用了来自 Facebook 的 Hydra 进行尝试。
* 服务打包：我们使用 Docker 对机器学习服务进行打包，其中的模型部分也会从 MLFlow 中载入。
* 模型服务：使用最简单的 K8s 托管的容器进行服务，web 框架选择了 FastAPI。
* 网络路由：选用了更加“现代化”的 Traefik，统一在 pulumi 中配置管理，非常方便。
* 持续集成：直接利用 Github actions，代码提交后自动执行测试与部署，流畅。
