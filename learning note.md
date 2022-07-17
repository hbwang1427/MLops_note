# MLops
* data management
* modeling and experiments

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
