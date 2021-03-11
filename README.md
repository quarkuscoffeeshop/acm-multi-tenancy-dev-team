# ACM Multi Tenancy dev team repo
See management repo [acm-multi-tenancy](https://github.com/quarkuscoffeeshop/acm-multi-tenancy).

## Getting Started
* Fork the following repo for devteam
  - https://github.com/quarkuscoffeeshop/acm-multi-tenancy-dev-team

##  Update devteam name
### Commands for dev-team-1
**This is in reference to the configuration [dev-team-1](https://github.com/tosin2013/acm-multi-tenancy#commands-for-dev-team-1) in the [ACM SRE GitRepo](https://github.com/tosin2013/acm-multi-tenancy)**
```
# Dev environment
$ sed -i '' -e 's/changeme/devteam1/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i '' -e 's/changeme/devteam1/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i '' -e 's/changeme/devteam1/g' prod/quarkuscoffeeshop/subscription.yml

```

### Commands for dev-team-2
**This is in reference to the configuration [dev-team-2](https://github.com/tosin2013/acm-multi-tenancy#commands-for-dev-team-2) in the [ACM SRE GitRepo](https://github.com/tosin2013/acm-multi-tenancy)**
```
# Dev environment
$ sed -i '' -e 's/changeme/devteam2/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i '' -e 's/changeme/devteam2/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i '' -e 's/changeme/devteam2/g' prod/quarkuscoffeeshop/subscription.yml

```

### Commands for dev-team-3
**This is in reference to the configuration [dev-team-3](https://github.com/tosin2013/acm-multi-tenancy#commands-for-dev-team-3) in the [ACM SRE GitRepo](https://github.com/tosin2013/acm-multi-tenancy)**
```
# Dev environment
$ sed -i '' -e 's/changeme/devteam3/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i '' -e 's/changeme/devteam3/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i '' -e 's/changeme/devteam3/g' prod/quarkuscoffeeshop/subscription.yml
```

# To Reset values
```
# Dev environment
$ sed -i '' -e 's/devteam[0-9]/changeme/g'  dev/quarkuscoffeeshop/subscription.yml

# Staging environment
$ sed -i '' -e 's/devteam[0-9]/changeme/g' staging/quarkuscoffeeshop/subscription.yml

# Prod environment
$ sed -i '' -e 's/devteam[0-9]/changeme/g' prod/quarkuscoffeeshop/subscription.yml
```

## Enviornments

### Dev
```
oc create -f dev/quarkuscoffeeshop/subscription.yml
```

### Staging
```
oc create -f staging/quarkuscoffeeshop/subscription.yml
```

### Prod
```
oc create -f prod/quarkuscoffeeshop/subscription.yml
```


### To-Do
```
oc create -f dev/homeoffice/subscription.yml
oc create -f staging/homeoffice/subscription.yml
oc create -f prod/homeoffice/subscription.yml
```
