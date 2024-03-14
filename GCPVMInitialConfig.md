# Startup, Configuration and Shutdown of Virtual Machine with Google Cloud Platform
> [!NOTE]
> The URL when working on GCP is https://console.cloud.google.com

## Deploying Machine Image into Virtual Machine
> Machine Image: stores configurations, metadata, permissions and data

1. Begin with selecting a project or creating a new project.
2. Once selected, click on the Hamburger icon in the top left of the page:
![Hamburger Icon](https://github.com/jsteinma/TechnicalLogs/assets/146376062/5fb30511-17b5-4016-b695-8bfc8703ff1a).
3. Under 'Compute Engine', select 'VM Instances' (Select 'Enable' if not enabled).
4. Select "Create Instance" on top taskbar.
5. Go through settings and set needed settings.
6. Click 'Create'.
> [!IMPORTANT]
> This will start the virtual machine and begin using credits.

7. To get username and password for VM, click on the dropdown arrow under connect of your specific VM instance:
![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/4e9409b2-cc55-4f92-a32f-f68d143d72b5)
8. Select 'Get Windows Password' and continue prompts, filling out required information, followed by selecting 'Set'.
9. A password will be generated and shown to you.
> [!WARNING]
> **Record this password** as it will not be shown again in future startups.

> [!IMPORTANT]
> The 'External IP' address for specific VM instance will change after every start/stop session.

## GCP Firewall Configuration
1. On 'VM Instances' screen under 'Related Actions', select "Set Up Firewall Rules".
2. Select "Create Firewall Rule" on top taskbar.
3. Name and set settings needed for firewall rule (allowed IP addresses, ports, etc.).
4. Click 'create'.

## Open Mirtual Machine
1. In start menu in local computer, search 'Remote Desktop Connection'.
2. Under 'Computer', enter 'External IP' number found on GCP under specific VM instance.
3. Select 'Connect'.
4. Ensure login is correct for required session (i.e. student)
5. Click 'Start'

## Virtual Machine Firewall Configuration
> [!NOTE]
> These instructions are for when using a **Windows** virtual machine.

1. With virtual machine open, search 'Windows Defender Firewall with Advanced Security'.
2. Cick 'Inbound Rules' and select 'New Rule'.
3. Set rule type parameters, click 'Next', and continue this process with filling out parameters until see 'OK'.

## Shutting Down Server
### On GCP
1. Under 'compute engine' select 'VM Instances' and under the 'More Actions' 3 vertical dots on the side of specific/running VM, select 'Stop':
![image](https://github.com/jsteinma/TechnicalLogs/assets/146376062/19d6a395-70ee-4407-baa6-e2c73addc459)

### On *Windows VM/Server
1. Go to start menu and click 'Shut Down' within virtual machine.

> [!TIP]
> When logging out of virtual machine inctead of shutting down, the server will still be accessible by ArcGIS Rest Services but will not be if shut down.
