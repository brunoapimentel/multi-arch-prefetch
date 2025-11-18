# Proof of concept for a multi-arch prefetch pipeline

## How to run the example

1. Run a [kind cluster](https://kind.sigs.k8s.io/docs/user/quick-start/) locally and install the [Tekton operator](https://tekton.dev/docs/installation/pipelines/)

2. Apply the pipeline definitions

    ```
    kubectl apply -f ./tekton
    ```

3. Create a Quay.io push secret, update the `service-account.yaml` with its name, and apply it to the cluster.

    ```
    kubectl apply -f my-quay-io-secret.yaml
    kubectl apply -f service-account.yaml
    ```

4. Run the pipeline

    ```
    kubectl create -f pipeline-run.yaml
    ```

## Results of the preliminary investigation

See the [investigation document](./INVESTIGATION.md).