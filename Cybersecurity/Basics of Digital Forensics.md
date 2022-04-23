**Website containg DFIR Tooling, Digital Forensics tutorials and guids from system forensics in windows, linux an max, etc.**
https://awesomedfir.com

**DFIR Training Path by awesomedfir.com (Train-hard)**
https://awesomedfir.com/get-ready-to-train-hard

**Digital Forensics Tools**
https://awesomedfir.com/dfir-tooling

# Live Acquisition
##### Risks of live Acquisitions
Collection process has a risk of making changes to the system. It is recommended to do an automated process.
	*Other Risks include:*
	- ***Business disruption*** - E.g. it slows down a machine in use of the business.
	- ***Destroying of the evidence*** - The possibility of data being overwritten if a write blocker is not used.
	- ***Alerting an attacker***
	- ***System creashed /BSOD(B**lue **S**creen **O**f **D**eath)***

##### When to Conduct a Live Acquisition
+ If you have a reason to believe volatile data contains information critical to the investigation that is not present elsewhere.
+ The acquisition can be run in an ideal manner; minimising changes to the target system.
+ Numerous systsms affected, making Forensics Imaging unfeasible.
+ Short timeline
+ Legal considerations that make it a recommended action to ensure as mush data is preserved.

**Some Drawbacks of performaing a live acquisition:
+ The target system could be sensitive to performance issues
+ The failure of the system could impact investigation
+ The target system may not have undergone testing to ensure the tools are compatible
+ Approval is recommended.

**What to Collect?**
*1st Category*
- Currently running state of the system:
	- Network Connections
	- Running Processes

*2nd Category*
- Snapshot type data:
	- File listing
	- System Logs
	- OS data
	- Application data


#