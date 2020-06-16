# Exercise 2: Getting started with On-Prem Kubernetes Cluster
In the provided lab environment, you would already have one Windows 10 machine running with Kubernetes Cluster already deployed and running. In this exercise, we’ll connect to the VM and check the existing Kubernetes Cluster

## Task 1: Verify existing Kubernetes Cluster
In this task, you will check the existing Kubernetes cluster and verify that the cluster is up and running. 
1. On Azure portal, search for **Azure Arc** from search box and then select the **Machines – Azure Arc**.

   ![](./images/azure-arc-1778.png) 

2. You will see, following two machines are **pre-connected**
   * **pre-connected-ubuntu**
   * **pre-connected-winvm**

   ![](./images/azure-arc-1779.png)

3. Click on one of the **pre-connected** machines.

   ![](./images/azure-arc-1991.png) 

4. From here, you can **manage** and **govern** your machines with **Manage access** and **Assess compliance**. You will explore on that next exercises.

   ![](./images/azure-arc-1781.png)
   
In this exercise, you explored about how to check the already onboarded Hybrid compute servers. In next exercise, you will explore more on onboarding the Azure Arc/Hybrid compute on-prem servers to Azure Arc.
