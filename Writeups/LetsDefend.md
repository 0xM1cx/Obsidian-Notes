## PowerShell Script | LetsDefend.io Challenge
### Scenario
You've come across a puzzling Base64 script, seemingly laced with malicious intent. Your mission, should you choose to accept it, is to dissect and analyze this script, unveiling its true nature and potential risks. Dive into the code and reveal its secrets to safeguard our digital realm. Good luck on this daring quest!



From viewing the text file you can see its a PowerShell command that executes a script
![[Pasted image 20240102212923.png]]

Decoding the Base64 encoded string we get this:
![[Pasted image 20240102213549.png]]
1. What encoding is the malicious script using?
	- ` Base64`
2. What parameter in the PowerShell script makes it so that the PowerShell window is hidden when executed?
	- `-W Hidden`
3. What parameter in the PowerShell script prevents the user from closing the process?
	- `-NonI`
4. What line of code allows the script to interact with websites and retrieve information from them?
	- `$WC=New-Object SySTeM.NET.WebCliENt`
5. What is the user agent string that is being spoofed in the malicious script?
	- `Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko`
6. What line of code is used to set the proxy credentials for authentication in the script?
	- `$wc.PROxY.CrEdenTialS = [SysTem.NEt.CRedeNTIALCAcHE]::DeFAULTNetWOrKCredENTiAls`
7. When the malicious scripts is executed, what is the URL that the script contacts to download the malicious payload?
	- `http://98.103.103.170:7443/index.asp`