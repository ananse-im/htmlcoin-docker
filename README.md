# htmlcoin-docker


# Docker Images
__ananseim/htmlcoin__  
htmlcoin daemon

__ananseim/htmlcoincore-deps__  
htmlcoind, zeromq, nodejs

__ananseim/htmlcoincore-node__  
htmlcoin-api

__ananseim/htmlcoincores-services__  
htmlcoin-api and htmlcoin-explorer


# Secret
Create kubernetes secret for htmlcoin-notification

```
kubectl create secret generic htmlcoin-secret --from-file=htmlcoin-wallet-firebase-adminsdk.json
```