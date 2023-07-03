# OpenShift 3scale Install

OpenShift 3scale installation script and notes.

## Steps

1. Install OpenShift 3scale via Operator Hub and wait for completion
2. Install OpenShift 3scale APIcast Gateway via Operator Hub and wait for completion
3. Create an S3 bucket in AWS (example below uses `3scale-demo`)
4. Gather AWS Access Key ID and AWS Secret Key
5. Get OpenShift `*.apps` domain
6. Run template with values you gathered in above steps

    ```shell
    oc process -f ./install.yaml \
    -p AWS_ACCESS_KEY_ID=AKIAIOSFODNN7EXAMPLE \
    -p AWS_SECRET_ACCESS_KEY=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY \
    -p AWS_BUCKET=3scale-demo \
    -p AWS_REGION=us-east-1 \
    -p OCP_APPS_DOMAIN=apps.cluster.foo.bar.example.com \
    | oc create -f -
    ````
