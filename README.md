
# Sentinel-Honeypot
## Detecting brute-force attack and mapping it to IP Geolocation 
![s2](https://user-images.githubusercontent.com/101039172/192967964-d5274c06-0236-4785-bcc8-09cc3d48f417.PNG)

### Objective

#### Extracting failed login using a custom PowerShell script to extract metadata from windows event viewer to be forwarded to third-party API to derive geo-location.
#### Configure log analytics workspace to ingest custom logs to map geo data in Azure Sentinel (SIEM).
#### Implement Azure Sentinel workbooks to display global attack data (RDP brute force) on world map displaying location and magnitude of attacks.
![sentinel1](https://user-images.githubusercontent.com/101039172/192967006-f1b83568-33ce-4ad3-a76c-856aa6d8c0e6.png)

The PowerShell script used in this demo runs live on the VM (named honeypot) deployed on Azure. The honeypot VM is kept open, and the firewall is turned off. Anyone from any part of the world can RDP into the VM. We will observe live attacks (RDP Brute Force) from all around the world. I will use a custom PowerShell script to extract the attackers Geolocation information and plot it on an Azure Sentinel as a world map!

## Languages Used
#### Powershell: To extract RDP failed logs from Windows Event Viewer (script should be running live)

## Third-party tool
#### ipgeolocation.io: API to map IP addresses to Geolocation

## Attacks from various locations; Custom logs being output with geo-location

![s3](https://user-images.githubusercontent.com/101039172/193174438-13c4c9c2-4fda-4f90-8b88-ddd4e2e06f9a.PNG)

## Windows logs are streamiled to Azure Log Analytics Workspace 
Connect the VM to the log analytic wokspae. Create custom logs by uploading the login_failed (files attached). Add the created log analytics workspace to Azure Sentinel and crete workbooks to run a query (query file attached)

![S4](https://user-images.githubusercontent.com/101039172/193174598-5cb9e06e-05ec-48e1-bd7d-d98826a5164b.png)

## RDP brute-force attacks from various locations displayed on Azure Sentinel 

![rdp_fail](https://user-images.githubusercontent.com/101039172/193174762-8e25331b-c345-45a3-b563-0a0028d3816f.PNG)

The powershell script was live and the above result was collected after 4 hours.

