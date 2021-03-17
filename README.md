# ACM Multi Tenancy dev team repo
See management repo [acm-multi-tenancy](https://github.com/quarkuscoffeeshop/acm-multi-tenancy).

## Getting Started
* Fork the following repo for devteam
  - https://github.com/quarkuscoffeeshop/acm-multi-tenancy-dev-team

## Set Contexts for deployment Environments 

### ACM Cluster 
```
oc login -u admin -p XXXX --insecure-skip-tls-verify https://api.YOURCLUSTER1.DOMAIN:6443
oc config rename-context $(oc config current-context) hubcluster
```

### Configure context for DEV Environment
```
oc login -u admin -p XXXX --insecure-skip-tls-verify https://api.YOURCLUSTER1.DOMAIN:6443
oc config rename-context $(oc config current-context) dev
```

### Configure context for Staging Environment
```
oc login -u admin -p XXXX --insecure-skip-tls-verify https://api.YOURCLUSTER1.DOMAIN:6443
oc config rename-context $(oc config current-context) staging
```

### Configure context for Production Environment
```
oc login -u admin -p XXXX --insecure-skip-tls-verify https://api.YOURCLUSTER1.DOMAIN:6443
oc config rename-context $(oc config current-context) prod
```

## Collect Domain Information for target Environments 
### Configure DOMAIN for DEV Environment
```
$ echo "Staging environment: $(oc --context=dev  get ingresses.config.openshift.io cluster -o jsonpath='{ .spec.domain }' | sed 's/apps.//')"
$ DOMAIN=$(oc --context=dev  get ingresses.config.openshift.io cluster -o jsonpath='{ .spec.domain }' | sed 's/apps.//')
$ sed  -i  "s/ocp4.example.com/${DOMAIN}/g"  dev/quarkuscoffeeshop/subscription.yml
```

### Configure DOMAIN for Staging Environment
```
$ echo "Staging environment: $(oc --context=staging  get ingresses.config.openshift.io cluster -o jsonpath='{ .spec.domain }' | sed 's/apps.//')"
$ DOMAIN=$(oc --context=staging  get ingresses.config.openshift.io cluster -o jsonpath='{ .spec.domain }' | sed 's/apps.//')
$ sed -i  "s/ocp4.example.com/${DOMAIN}/g" staging/quarkuscoffeeshop/subscription.yml
```

### Configure DOMAIN for DEV Environment
```
$ echo "Staging environment: $(oc --context=prod  get ingresses.config.openshift.io cluster -o jsonpath='{ .spec.domain }' | sed 's/apps.//')"
$ DOMAIN=$(oc --context=prod  get ingresses.config.openshift.io cluster -o jsonpath='{ .spec.domain }' | sed 's/apps.//')
$ sed  -i  "s/ocp4.example.com/${DOMAIN}/g"  prod/quarkuscoffeeshop/subscription.yml
```


##  Update devteam and database info
### Commands for dev-team-1
**This is in reference to the configuration [dev-team-1](https://github.com/tosin2013/acm-multi-tenancy#commands-for-dev-team-1) in the [ACM SRE GitRepo](https://github.com/tosin2013/acm-multi-tenancy)**
```
$ CLUSTER_ENV=dev  #ex. staging, prod # password will be different for different envs
$ POSTGRES_DEVTEAM1='CHANGEPASSWORD'
$ sed -i "s|'changepassword'|'${POSTGRES_DEVTEAM1}'|g" ${CLUSTER_ENV}/quarkuscoffeeshop/subscription.yml
$ cat staging/quarkuscoffeeshop/subscription.yml

# Dev environment
$ sed -i 's/changeme/devteam1/g'  dev/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/changeme/devteam1/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i  's/changeme/devteam1/g' staging/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/changeme/devteam1/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i  's/changeme/devteam1/g' prod/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/changeme/devteam1/g' prod/quarkuscoffeeshop/subscription.yml

```

### Commands for dev-team-2
**This is in reference to the configuration [dev-team-2](https://github.com/tosin2013/acm-multi-tenancy#commands-for-dev-team-2) in the [ACM SRE GitRepo](https://github.com/tosin2013/acm-multi-tenancy)**
```
$ CLUSTER_ENV=dev  #ex. staging, prod # password will be different for different envs
$ POSTGRES_DEVTEAM2='CHANGEPASSWORD'
$ sed -i "s|'changepassword'|'${POSTGRES_DEVTEAM2}'|g" ${CLUSTER_ENV}/quarkuscoffeeshop/subscription.yml
$ cat staging/quarkuscoffeeshop/subscription.yml

# Dev environment
$ sed -i  's/changeme/devteam2/g'  dev/quarkuscoffeeshop/subscription.yml
## On MAC
$ sed -i '' -e 's/changeme/devteam2/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i 's/changeme/devteam2/g' staging/quarkuscoffeeshop/subscription.yml
## On MAC
$ sed -i '' -e 's/changeme/devteam2/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i 's/changeme/devteam2/g' prod/quarkuscoffeeshop/subscription.yml
## On MAC
$ sed -i '' -e 's/changeme/devteam2/g' prod/quarkuscoffeeshop/subscription.yml

```

### Commands for dev-team-3
**This is in reference to the configuration [dev-team-3](https://github.com/tosin2013/acm-multi-tenancy#commands-for-dev-team-3) in the [ACM SRE GitRepo](https://github.com/tosin2013/acm-multi-tenancy)**
```
$ CLUSTER_ENV=dev  #ex. staging, prod # password will be different for different envs
$ POSTGRES_DEVTEAM3='CHANGEPASSWORD'
$ sed -i "s|'changepassword'|'${POSTGRES_DEVTEAM3}'|g" ${CLUSTER_ENV}/quarkuscoffeeshop/subscription.yml
$ cat prod/quarkuscoffeeshop/subscription.yml

# Dev environment
$ sed -i 's/changeme/devteam3/g' dev/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/changeme/devteam3/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i 's/changeme/devteam3/g' staging/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/changeme/devteam3/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i 's/changeme/devteam3/g' prod/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/changeme/devteam3/g' prod/quarkuscoffeeshop/subscription.yml
```

# To Reset values
```
# Dev environment
$ sed -i 's/devteam[0-9]/changeme/g'  dev/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/devteam[0-9]/changeme/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i 's/devteam[0-9]/changeme/g' staging/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/devteam[0-9]/changeme/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i 's/devteam[0-9]/changeme/g' prod/quarkuscoffeeshop/subscription.yml

## On MAC
$ sed -i '' -e 's/devteam[0-9]/changeme/g' prod/quarkuscoffeeshop/subscription.yml
```

## Deploy Helm chart to Target Enviornments

### Dev
```
oc --context=hubcluster create -f dev/quarkuscoffeeshop/subscription.yml
```

### Staging
```
oc --context=hubcluster create -f staging/quarkuscoffeeshop/subscription.yml
```

### Prod
```
oc --context=hubcluster create -f prod/quarkuscoffeeshop/subscription.yml
```

### expose route on Hub Clusters
**For devteam1**
```
$ CLUSTER_ENV=dev  #ex. staging, prod 
$ oc --context=${CLUSTER_ENV} expose svc/quarkuscoffeeshop-web -n quarkuscoffeeshop-devteam1-gitops
```

**For devteam2**
```
$ CLUSTER_ENV=dev  #ex. staging, prod 
$ oc --context=${CLUSTER_ENV} expose svc/quarkuscoffeeshop-web -n quarkuscoffeeshop-devteam2-gitops
```

**For devteam3**
```
$ CLUSTER_ENV=dev  #ex. staging, prod 
$ oc --context=${CLUSTER_ENV} expose svc/quarkuscoffeeshop-web -n quarkuscoffeeshop-devteam3-gitops
```

### To-Do
```
oc create -f dev/homeoffice/subscription.yml
oc create -f staging/homeoffice/subscription.yml
oc create -f prod/homeoffice/subscription.yml
```
