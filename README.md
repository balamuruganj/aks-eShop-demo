Please refer the wiki section for the deployment. 

To apply the HPA, please run the below in yourAKS console. 

Edit the deployment of eshop-webspa and eshop-catalog-api and assign the following in the resource section. 

    resources:
          limits:
            cpu: 200m
          requests:
            cpu: 100m

Run the following commands. 

kubectl autoscale deployment eshop-webspa --cpu-percent=5 --min=1 --max=10

kubectl autoscale deployment eshop-catalog-api --cpu-percent=5 --min=1 --max=10
