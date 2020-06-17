# Exercise 4: Deploy Sample Kubernetes App through Azure Arc

## Task 1: Create a Configuration

1. Fork the repository https://github.com/Azure/arc-k8s-demo to your personal github account as this is used in the later part of the lab.

## Task 2: Deploy App using az k8sconfiguration

1. Using the Azure CLI extension for k8sconfiguration, link connected cluster to personal git repository. Provide this configuration a name cluster-config, instruct the agent to deploy the operator in the cluster-config namespace, and give the operator cluster-admin permissions. 

2. Run the following command
   - Replace the XXXXXX with the deploymentID provided in the environment details page
   - Replace the **your personal github account name** with your personal github account that you are using to perform the lab.

   ```
   az k8sconfiguration create --name cluster-config --cluster-name AzureArcAKSCluster1 --resource-group Azure-Arc-XXXXXX --operator-instance-name cluster-config --operator-namespace cluster-config --repository-url https://github.com/<your personal github account name>/arc-k8s-demo --scope cluster --cluster-type connectedClusters
   ```
   The output should be as shown:

   ![](./images/azure-arc-08.png) 

## Task 3: Validate the sourceControlConfiguration

1. Validate whether the sourceControlConfiguration was successfully created.

   ```
   az k8sconfiguration show --resource-group Azure-Arc-XXXXXX --name cluster-config --cluster-name AzureArcAKSCluster1 --cluster-type connectedClusters
   ```
   Note that the sourceControlConfiguration resource is updated with compliance status, messages, and debugging information in the output.

   The output should be as shown:

   ![](./images/azure-arc-09.png) 
  
   >Wait for 5 mins before performing the next step
  
2. Navigate to **Azure-Arc RG->AzureArcAKSCluster1->Configurations**. The operator state status should show as **installed**

   ![](./images/azure-arc-10.png) 
  
## Task 4:  Validate the Kubernetes configuration

1. After config-agent has installed the flux instance, resources held in the git repository should begin to flow to the cluster. Check to see that the namespaces, deployments, and resources will be created by **Running the following command:**

   ```
   kubectl get ns --show-labels
   ```
 
   The output shows that team-a, team-b, itops, and cluster-config namespaces have been created as shown:
  
   ![](./images/azure-arc-11.png) 
   
 2. The flux operator will be deployed to cluster-config namespace, as directed by our sourceControlConfig:
      
    ```
    kubectl -n cluster-config get deploy  -o wide
    ```
   
    The output is as shown:
   
    ![](./images/azure-arc-12.png) 
  
3. You can explore the other resources deployed as part of the configuration repository by following commands:

   ```
   kubectl -n team-a get cm -o yaml
   ```
   ```
   kubectl -n itops get all
   ```
