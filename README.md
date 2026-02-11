# Kubearchive Tekton PipelineRun logs

These scripts extend the functionality of the [kubearchive plugin](https://github.com/kubearchive/kubearchive) for `kubectl` to list logs of Pods (tasks) and PipelineRun.

The tool looks either for `oc` or `kubectl`, but you can override the program path with `KUBEARCHIVE_PR_LOGS_KUBECTL` environment variable.

## Usage

Make sure to set the address of the Kubearchive server and log in to the cluster:

```sh
export KUBECTL_PLUGIN_KA_HOST=https://kubearchive-api-server-product-kubearchive...
oc login --web https://api...:6443
```

List logs of a PipelineRun:

```sh
oc ka pr logs <pipeline_run_name>
```

List logs of a specific pod (Tekton task):

```sh
oc ka pod logs <component_name>-<pipeline_name>-<task_name>-pod
```
