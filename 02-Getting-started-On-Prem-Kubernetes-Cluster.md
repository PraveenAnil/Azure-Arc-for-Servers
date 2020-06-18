# Exercise 2: Getting started with On-Prem Kubernetes Cluster
In the provided lab environment, you would already have one Windows 10 machine running with Kubernetes Cluster already deployed and running. In this exercise, we’ll connect to the VM and check the existing Kubernetes Cluster

## Task 1: Verify existing Kubernetes Cluster
In this task, you will check the existing Kubernetes cluster and verify that the cluster is up and running. 

1. Open **Visual Studio Code**

   ![](./images/arc-01.png) 

2. Click on the **Kubernetes** icon and verify whether the cluster **minikube** is present,explore the different features available.
   
   ![](./images/arc-02.png) 
   
3. Open the **Powershell terminal** within the Visual studio code .
    
   ![](./images/arc-03.png) 

4. Run the following command to check the status of the cluster .
   
   ```
   minikube status
   ```
   If the cluster is running, the output from minikube status should be similar to:
   
   ![](./images/arc-04.png) 
   
   >Note: If the cluster status is **Stopped**,Run the following commands
   
   ```
   minikube delete
   ```
   
   ```
   minikube start
   ```
## Task 2: Configuring WSL environment on Windows
   
 1. Open the **Ubuntu 18.04** as a administrator
   
    ![](./images/arc-05.png)  
    
 2. If prompted with username and Password provide the username as **arcadmin** and Password as **Password.1!!** and wait until the application is installed.
 
    ![](./images/arc-06.png) 
  
## Task 3:Connect to Kubernetes cluster using WSL

In this exercise, you explored about how to check the already onboarded Hybrid compute servers. In next exercise, you will explore more on onboarding the Azure Arc/Hybrid compute on-prem servers to Azure Arc.
