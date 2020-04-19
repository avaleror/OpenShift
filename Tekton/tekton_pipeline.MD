Demo Tekton Pipelines

An OpenShift cluster will be needed, an admin account and the tkn CLI.

Create a project in OCP or a namespace in Kubernetes named tekton(if you decide to change the name change it also in file 04), execute the files in numerical order to create the resources.
Execute these commands:

tkn pipeline start build-and-deploy \
    -r git-repo=api-repo \
    -r image=api-image \
    -p deployment-name=vote-api

tkn pipeline start build-and-deploy \
    -r git-repo=ui-repo \
    -r image=ui-image \
    -p deployment-name=vote-ui

After executing the commands the pipeline will be running, wait until both commands finish.
You should have a voting app deployed in your cluster with two pods, a backend pod and an UI pod.
