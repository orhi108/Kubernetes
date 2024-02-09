## Introduction

In order isolated Kubernetes namespace creation for specific usecase it RBAC setup is required to be configured. As well as namespace resource limitation is acheived with quatas. In this example the task is acheived with creation of custome templates which by the help of a script can be deployed easily.


## List of template files:

Following short listed files are acting as templates. At the moment they are with basic functionality and they can be modified and enriched with more features and options. They are added in a list in to the script so in case other template need to be added then that this amended in the the apply script as well.

- namespace.yaml  
- networkpolicy.yaml  
- quota.yaml  
- role.yaml  
- rolebinding.yaml

## Usage of apply script

In this particular case shell script ```apply.sh``` is created which cosist itself parameters which need to be configured for the particular namespace. 

In the following map arrat need to be specified the namespace name and the user name which will be handle the usecase namespace and resources:

Example:
```
declare -A values=(
    [namespace]=usecase1 
    [username]=username
)
```

Then the script itself needs to be executed in order to create and configure the usecase namespace. 

Example:

```
./apply.sh [yes]
```

```yes``` option in required for confirmation of the real deployment, by default it is just dry run. And showing the customised kubernetes definition files. 
