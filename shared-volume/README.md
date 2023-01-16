# shared-volume

## How to deploy
```
kubectl apply -k ./shared-volume
```

## How to try
1. Get pod of app_1 or app_2
```
kubectl get pods --namespace platform
```
2. Run this command
```
kubectl exec --namespace platform -it app-one-h4sh3d-n4m3 -- touch /usr/share/echo-file/shared-file.echo
```
3. Port forward app_1 and app_2, to access via localhost
run this command:
```
kubectl port-forward deployment/app-one 3001:3000 --namespace platform
```
open another terminal tab and run this command:
```
kubectl port-forward deployment/app-two 3002:3000 --namespace platform
```
4. Ready for Read and Write
detailed [here](https://github.com/satyasyahputra/echo-file).