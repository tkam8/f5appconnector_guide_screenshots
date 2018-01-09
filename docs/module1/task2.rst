Get information required for node auto discovery
=============================

The Proxy needs permission to automatically discover nodes in Microsoft Azure. 
To set this permission, the Proxy requires an azure_config.json file, which contains 
the credentials to sign HTTP requests to Azure. Without this information, you may 
receive an authentication error in the Application Connector proxy. 

#. Create a service principal by using the instructions Microsoft provides:
    https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal

#. In the /home/<user>/cloud_vendors/azure directory on the Linux instance where you are 
    installing Application Connector Proxy, create a new text file named azure_config.json, and add
    these four variables:

     .. code-block:: JSON
        :linenos:

         {    
            "TENANT":"your tenant ID",
            "AZURE_SUBSCRIPTION_ID":"your azure subscription ID",
            "CLIENT_ID":"client or application ID",
            "APPLICATION_SECRET":"client or application secret (service principle)"
         }


Your Azure environment should now be ready to deploy Application Connector.