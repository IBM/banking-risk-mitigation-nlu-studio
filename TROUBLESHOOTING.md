# TROUBLESHOOTING
## If you encounter an error while cloning the repo

While following the instructions to clone the repo, you may encounter-

![](https://github.com/IBM/banking-risk-mitigation-nlu-studio/blob/master/doc/source/images/clone_error.png)

In this case run:

```
git clone 
```

## If you encounter an error while logging into your ibmcloud account

You might be using a federated account, run:

```
ibmcloud login --sso
```


## To troubleshoot your IBM Cloud application, use the logs. 

To see the logs, run:

```bash
ibmcloud cf logs Client_Network_Banking_V1 --recent
```

## 
