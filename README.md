# ArgoWorkflowTemplateRepo

In this repository, we will list all templates which is available for the argo workflow instance of SSP Datalab.

For now, we divide all templates into two categories. In folder tasks, we hosts templates which are common modular 
tasks which can be re-used in a workflow. For example, the task template which detects duplicated rows should locate
in this folder. In folder workflows, we hosts templates which covers an entire workflow. 
It means by invoking such template, you can accomplish a full data pipeline.  

Each template should have a main folder that contains three sub-directory. The following example show the directory 
organization of a template.
``` bash
└── shell-executor
    ├── argo-example
    │   └── call-shell-executor.yaml
    ├── argo-template
    │   └── shell-executor-argo-template.yaml
    └── helm-chart
        ├── Chart.yaml
        ├── templates
        │   └── simpleJob.yaml
        ├── values.schema.json
        └── values.yaml
```

The main folder name is the name of the argo template. The sub-folder **argo-template** contains the code source
of the argo template. The sub-folder **argo-example** contains an argo workflow example that invokes the template.
The sub-folder **helm-chart** hosts a helm to run a workflow by using **helm install**