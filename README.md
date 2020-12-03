# kustomize-with-multiple-envs

Kustomize example with multiple environment variables.

There are 3 examples in this repo:

## overlays/dev

First example shows how to use shared environment variables from the base folder and separate environment variables from the overlay folder as config-map.

```bash
# Generate .yaml files
kustomize build ./overlays/dev

# Deploy
kustomize build ./overlays/dev | kubectl apply -f -
```

## overlay/pre-prod

Second example shows how to combine/patch the shared env variables, by adding custom environment variables from the overlay folder as a config-map.

```bash
# Generate .yaml files
kustomize build ./overlays/pre-prod

# Deploy
kustomize build ./overlays/pre-prod | kubectl apply -f -
```

## overlays/prod

Third example hows how to use shared/generic environment variables from the base folder and combine multiple environment variables from different files within an overlay folder as a config-map.

```bash
# Generate .yaml files
kustomize build ./overlays/prod

# Deploy
kustomize build ./overlays/prod | kubectl apply -f -
```