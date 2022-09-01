
# Introduction to Phishing Analysis
---
Phishing attacks correspond to the "**Delivery**" phase in the **Cyber Kill Chain** model created to analyze cyber attacks. The delivery stage is the step where the attacker transmits the previously prepared harmful content to the victim systems / people.
![[Pasted image 20220503225804.png]]

> Phishing attacks is one of the most common attack vector for initial access.

# Information Gathering
---
## Spoofing 
Attackers can send emails on behalf of someone else, as the emails do not necessarily have an authentication mechanism. Attackers can send mail on behalf of someone else using the technique called spoofing to make the user believe that the incoming email is reliable

Several protocols have been created to prevent the Email Spoofing technique. With the help of <u>SPF(Sender Policy Framework)</u>, <u>DKIM(DomainKeys Identified Mail)</u> and DMARC protocols, it can be understood whether the sender's address is fake or real. Some mail applications do these checks automatically. However, the use of these protocols is not mandatory and in some cases can cause problems.

## E-mail Traffic Analysis
Many parameters are needed when analyzing a phishing attack. We can learn the size of the attack and the target audience in the search results to be made on the mail gateway according to the following parameters.
-   Sender Address(info@letsdefend.io)
-   SMTP IP Address(127.0.0.1)
-   @letsdefend.io (domain base)
-   letsdefend (Besides the gmail account, attacker may have sent from the hotmail account)
-   Subject (sender address and SMTP address may be constantly changing)

# What is an Email Header and How to Read Them?
---

## What is an Email Header?
"**Header**" is basically a section of the mail that contains information such as *sender*, *recipient* and *date*. In addition, there are fields such as "**Return-Path**", "**Reply-To**", and "**Received**". Below you can see the header details of a sample email.
![[Pasted image 20220507172005.png]]

## What does the Email Header do?
**Enables Shipper and Recipient Identification**  

Thanks to the "From" and "To" fields in the header, it is determined from whom an email will go to whom. If we look at the email above that you downloaded in "eml" format, we see that it was sent from the address "ogunal@letsdefend.io"to "info@letsdefend.io"
![](https://letsdefend.io/blog/wp-content/uploads/2022/03/sample-subject.png)

**Spam Blocker**  
It is possible to detect spam emails using Header analysis and other various methods. This protects people from receiving SPAM emails.

**Allows Tracking an Email’s Route**  
It is important to check the route it follows to see if an email came from the right address. If we look at the sample email above, we see that it came from the "ogunal@letsdefend.io" address, but did it actually come from the "letsdefend.io" domain or from a different fake server that mimics the same name? We can use the header information to answer this question.

### Important Fields

**From**  
The "From" field in the internet header indicates the name and email address of the sender.

**To**  
This field in the mail header contains the email's receiver's details.
It includes their name and their email address. Fields like CC (carbon copy) and BCC (blind carbon copy) also fall under this category as they all include details of your recipients.  
If you want to find out more about carbon copy and blind carbon copy, check out how to use CC and BCC.  

**Date**  
This is the timestamp that shows when the email was sent.  
In Gmail, it usually follows the format of "day dd month yyyy hh:mmss  
So if an email had been sent on the *16th of November, 2021, at 4:57:23 PM*, it would show as *Wed, 16 Nov 2021 16:57:23*.

**Subject**  
The subject mentions the topic of the email. It summarizes the content of the entire message body.

**Return-Path**  
This mail header field is also known as **Reply-To**. If you reply to an email, it will go to the address mentioned in the Return-Path field.

**Domain Key and DKIM Signatures**  
The Domain Key and Domain Key Identified Mail (DKIM) are email signatures that help email service providers identify and authenticate your emails, similar to SPF signatures.

**Message-ID**  
The Message ID header field is a unique combination of letters and numbers that identifies each mail. No two emails will have the same Message ID.

**MIME-Version**  
**Multipurpose Internet Mail Extensions (MIME)** is an internet standard of encoding. It converts non-text content like images, videos, and other attachments into text so they can be attached to an email and sent through SMTP (Simple Mail Transfer Protocol).

**Received**  
The received field lists each mail server that went through an email before arriving in the recipient's inbox. It's listed in reverse chronological order — where the mail server on the top is the last server the email message went through, and the bottom is where the email originated.

**X-Spam Status**  
The X-Spam Status shows you the spam score of an email message.  
First, it'll highlight if a message is classified as spam. Then, the spam score of the email is shown, as well as the threshold for the spam for the email. An email can meet either the spam threshold of an inbox or exceed it. If it's too spammy and exceeds the threshold, it will automatically be classified as spam and sent to the spam folder.

# Email Header Analysis
---
Here are the key questions we need to answer when checking headings during a Phishing analysis:
1. Was the email sent from the correct SMTP server?
2. Are the data "**From**" and "**Return-Path / Reply-To**" the same?

- <u>Was the email sent from the correct SMTP server?</u>
We can check the "Received" field to see the path followed by the mail. As the image below shows, the mail is "101.99.94.116" from the IP address server.

![](https://app.letsdefend.io/static/img/received-header.PNG)
If we look at who is sending the mail ("sender"), we see that it came from the domain Letsdefend.io

![](https://app.letsdefend.io/static/img/email-from.PNG)
So under normal circumstances, "letsdefend.io" should use, "101.99.94.116" to send mail. To confirm this situation, We can query the MX servers actively used by "letsdefend.io"

"mxtoolbox.com" helps by showing you the MX servers used by the domain you searched.

![](https://app.letsdefend.io/static/img/mxtoolbox.PNG)

If we look at the image above, the "letsdefend.io" domain uses Google addresses as an email server. So there is no relationship with the emkei.cz or "101.99.94.116" addresses.

In this check, it was determined that the email did not come from the original address, but was spoofed.

- <u>Are the data "From" and "Return-Path / Reply-To" the same?</u>
Except in exceptional cases, we expect the sender of the e-mail and the person receiving the responses to be the same. An example of why these areas are used differently in Phishing attacks:

Someone sends an email (gmail, hotmail etc.) with the same last name of someone working for Google to LetsDefend, LetsDefend tells the employee that he has issued the invoice and they must make the payment to his XXX account. It puts the e-mail address of the real Google employee in the "Reply-to" field so that the fake e-mail address does not stand out in case of replying to a possible e-mail.

Returning to the e-mail we downloaded above, all we have to do is compare the email addresses in the "From" and "Reply-to" fields.  

![](https://app.letsdefend.io/static/img/reply-to.PNG)

As you can see, the data is different. In other words, when we want to reply to this e-mail, we will send a reply to the gmail address below. Just because this data is different doesn't always mean it's definitely a phishing email, we need to consider the event as a whole. In other words, in addition to this suspicious situation, if there is a harmful attachment, URL or misleading content in the e-mail content, we can understand that the e-mail is phishing. In the continuation of the training, we will analyze the data in the body part of the e-mail.
# Static Analysis
---
It is a fact that mails composed of plain text are boring. For this reason, mail applications provide HTML support, allowing the creation of mails that can attract more attention of users. Of course, this feature has a disadvantage. Attackers can create e-mails with HTML, hiding URL addresses that are harmful behind buttons / texts that seem harmless.
![[Pasted image 20220507182907.png]]
As seen in the image above, the address that the user sees can be different when the link is clicked (the real address is seen when the link is hovered).

>Attackers take a new domain address in most phishing attacks and do a phishing attack within a few days and finish their work. For this reason, if the domain name in the mail is new, it is more likely to be a phishing attack.

It is possible to find out whether the antivirus engines detect the web address as harmful by searching the web addresses in the mail on VirusTotal. If someone else has already analyzed the same address / file in VirusTotal, VirusTotal does not analyze from scratch, it shows you the old analysis result. We can use this feature both as an advantage and a disadvantage.

![](https://umuttosun.com/wp-content/uploads/2020/05/Screen-Shot-2020-05-04-at-05.07.11-1024x156.png)

If the attacker searches the domain address on VirusTotal without containing harmful content on it, that address will appear harmless on VirusTotal, and if it goes unnoticed, you may be mistaken for this address to be harmless. In the image above, you can see that umuttosun.com address appears harmless, but if you look at the section marked with the red arrow, you will see that this address was searched 9 months ago, and this result is 9 months ago. To have it analyzed again, the button marked with the blue arrow must be pressed.

If the page was previously searched on VirusTotal, it may mean that the attacker wanted to see the rate of detection of the site during the preparation phase. If we analyze it again, antivirus engine detects it as phishing, which means that the attacker has a move to trick analysts.

Performing static analysis of the files in the mail can enable the learning of the capacity / capabilities of that file. However, since static analysis takes a long time, you can get the information you need more quickly with dynamic analysis.

[Cisco Talos Intelligence](https://talosintelligence.com/) has search sections where we can learn reputations of IP addresses. By searching the SMTP address of the mail we detected on Talos, we can see the reputation of the IP address and find out whether it is included in the blacklist. If the SMTP address is in the blacklist, it can be understood that an attack was made on a compromised server.

![](https://umuttosun.com/wp-content/uploads/2020/05/Screen-Shot-2020-05-10-at-15.26.00-1-1024x453.png)

Likewise, the SMTP address can be searched on VirusTotal and AbuseIPDB to determine if the IP address has previously been involved in malicious activities.

# Dynamic Analysis
---
URLs and files can be found in the mail. These files and URL addresses need to be examined. You don't want your data to be stolen by hackers by running these files on your personal computer. For this reason, the websites and files in the mail should be run in sandbox environments and the changes made on the system should be examined, and it should be checked whether they are harmful or not.
![[Pasted image 20220507183849.png]]
If you want to quickly check the web addresses in the mail, you can see the content of the website using online web browsers such as [Browserling](https://www.browserling.com/). The good thing about such services is that you will not be affected by a possible zero-day vulnerability that affects browsers, since you do not go to the web page on your own computer. The disadvantage of using web browsers such as Browserling is that if the malicious file is downloaded on the site, you cannot run this file. For this reason, your analysis will be interrupted.
![[Pasted image 20220507183900.png]]

Before going to the addresses in the mail, it should be checked whether there is important information in the address. When we examine the example in the image above, when the user clicks on popularshoppingsite.com, it is seen that the address of the user is actually visited, and the email address of the user in the email parameter. Even if the user does not enter his / her password on the phishing page, it means that the link in the mail is accessed when this address is reached and the attacker understands that this user is valid. It can increase the success rate of the attack it will carry out by doing social engineering attacks over the users that are valid in the attacks it will carry out later. For this reason, it is necessary to change the information such as e-mail address before accessing the addresses.
![[Pasted image 20220507183914.png]]

<u>A few commonly used sandboxes: </u>
-   VMRay
-   Cuckoo Sandbox 
-   JoeSandbox
-   AnyRun
-   Hybrid Analysis(Falcon Sandbox)

> Malware can wait for a certain period of time without any action to make detection difficult. You must wait for the malware to work before you decide that the examined file is not harmful.

The fact that there are no urls and files in the mail does not mean that this is not harmful. The attacker can also send it as a picture so as not to get caught up in the analysis products.
# Additional Techniques
---
  
Another technique that attackers use is to perform phishing attacks using normally legal sites. Some of them are as follows.

**Using services that offer Cloud Storage services such as Google and Microsoft**

Attackers try to click on Google / Microsoft drive addresses that seem harmless to the user by uploading harmful files onto the drive.

**Using services that allow creating free subdomains such as Microsoft, Wordpress, Blogspot, Wix**

Attackers try to deceive security products and analysts by creating a free subdomain from these services. Since whois information cannot be searched as a subdomain, it can be seen that these addresses were taken in the past and belongs to institutions such as Microsoft, Wordpress.

**Form applications**

Services are available that allow free form creation. Attackers use these services instead of creating a fishing site themselves. Since the domain is harmless under normal conditions, it can pass on to the user without getting stuck on antivirus software. Google Form is an example of these services. When looking at **whois** information, the domain can be seen to be Google, so the attacker can mislead analysts.


```json
Note Title: "Phising Analysis",
Author: "Shawn Michael A Sudaria",
Github: "https://github.com/0xM1cx"
```


