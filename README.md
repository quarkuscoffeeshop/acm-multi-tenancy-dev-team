# ACM Multi Tenancy dev team repo


## Enviornments

### Dev
```
oc create -f dev/metrics-app/subscription.yml
oc create -f dev/cloudprober/subscription.yml
```

### Staging
```
oc create -f staging/metrics-app/subscription.yml
oc create -f staging/cloudprober/subscription.yml
```

### Prod
```
oc create -f prod/metrics-app/subscription.yml
oc create -f prod/cloudprober/subscription.yml
```