<h1>Deployed a hub-spoke network using Azure Bicep.</h1>



<h2>Description</h2>

-  Topology: A hub virtual network, two interconnected spokes, an Azure Firewall supporting availability zones and a Bastion host.
-  Resources deployed: Firewall (Standard SKU | 3PIPs in 3 Zones), Bastion (Basic | 1 PIP), 4 PIPs  in total (Standard | Regional), Route      Table (Next Hop to Hub FW Private IP), 3 NSGs, FW Policy(Standard | Deny), Log Analytics(Insights).
-  Vnet Peerings - Hub to vnet-spoke-one; Hub to vnet-spoke-two.
-  Hub Vnet - (AzureBastionSubnet, AzureFirewallSubnet, GatewaySubnet), NSG for Bastion.
-  Spoke Vnets - (Subnet for resources, Subnet for private link endpoints), 2 NSGs assigned to both subnets.

-  main.bicep template to define resources. 
-  Azuredeploy.parameters.json parameter file with the values to use to deploy bicep template.
-  Azure CLI command:
az deployment group create --name HubSpokeBicepDeployment --resource-group HubSpokeRG --template-file .\main.bicep --parameters .\azuredeploy.parameters.json

<br />


<h2>Languages used</h2>

- <b>Bicep Language</b> 
- <b>Azure CLI</b>


<h2>Environments Used </h2>

- <b>Vs Code</b>
- <b>Azure Portal</b> 

<h2>Network Topoloy </h2>

<img src="https://i.imgur.com/hBT1jqT.jpeg" height="80%" width="80%" alt="Network Topology"/>
<br />



