# tchelinux-2021
A presentation about Pulumi - Modern Infrastructure as Code for Tche Linux 2021


## Requirements
+ Python 3 
+ Pulumi CLI
+ Google Cloud Platform CLI


## Install Requirements

**Python 3**

```
$ brew install python
```

**Pulumi CLI**

```
$ brew install pulumi
```

**Google Cloud Platform CLI**

Please following the detailed instructions [here](https://cloud.google.com/sdk/docs/quickstart).


## Configuration

**Google Cloud Platform CLI**

Initialize the Cloud SDK:

```
$ gcloud init
```

To list accounts whose credentials are stored on the local system:

```
$ gcloud auth list
```

Set the project:

```
$ gcloud config set project PROJECT_ID
```

Check the default project:

```
$ gcloud config get-value project
```

**Pulumi**

Create new Pulumi project:

```
$ mkdir tchelinux-2021 && cd tchelinux-2021
$ pulumi new gcp-python
```

Define the GCP project:

```
$ pulumi config set gcp:project PROJECT_ID
```

Define the GCP Zone:

```
$ pulumi config set gcp:zone europe-north1-a
```

Deploy everything:

```
$ pulumi up
```

Curl the HTTP server:

```
$ curl $(pulumi stack output instanceIP)
```

SSH into the server:

```
$ gcloud compute ssh $(pulumi stack output instanceName)
```

Cleanup

```
$ pulumi destroy
$ pulumi stack rm
```
