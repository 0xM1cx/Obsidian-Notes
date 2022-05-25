### Features of Burpsuite Community
- **Proxy** -> the most well-know aspect of Burp Suite, the Burp Proxy allows us to intercept and modify requests/responses when interacting with web applications.
- **Repeater:** The second most well-known Burp feature -- [Repeater](https://tryhackme.com/room/burpsuiterepeater) -- allows us to capture, modify, then resend the same request numerous times. This feature can be absolutely invaluable, especially when we need to craft a payload through trial and error (e.g. in an SQLi -- **S**tructured **Q**uery **L**anguage **I**njection) or when testing the functionality of an endpoint for flaws.
-   **Intruder:** Although harshly rate-limited in Burp Community, [Intruder](https://tryhackme.com/room/burpsuiteintruder) allows us to spray an endpoint with requests. This is often used for bruteforce attacks or to fuzz endpoints.
-   **Decoder:** Though less-used than the previously mentioned features, [Decoder](https://tryhackme.com/room/burpsuiteom) still provides a valuable service when transforming data -- either in terms of decoding captured information, or encoding a payload prior to sending it to the target. Whilst there are other services available to do the same job, doing this directly within Burp Suite can be very efficient.  
-   **Comparer:** As the name suggests, [Comparer](https://tryhackme.com/room/burpsuiteom) allows us to compare two pieces of data at either word or byte level. Again, this is not something that is unique to Burp Suite, but being able to send (potentially very large) pieces of data directly into a comparison tool with a single keyboard shortcut can speed things up considerably.  
-   **Sequencer:** We usually use [Sequencer](https://tryhackme.com/room/burpsuiteom) when assessing the randomness of tokens such as session cookie values or other supposedly random generated data. If the algorithm is not generating secure random values, then this could open up some devastating avenues for attack.

In addition to the myriad of in-built features, the Java codebase also makes it very easy to write extensions to add to the functionality of the Burp framework. These can be written in Java, Python (using the Java [Jython](https://www.jython.org/) interpreter), or Ruby (using the Java [JRuby](https://www.jruby.org/) interpreter). The Burp Suite [Extender](https://tryhackme.com/room/burpsuiteextender) module can quickly and easily load extensions into the framework, as well as providing a marketplace to download third-party modules (referred to as the "BApp Store"). Whilst many of these extensions require a professional license to download and add in, there are still a fair number that can be integrated with Burp Community. For example, we may wish to extend the inbuilt logging functionality of Burp Suite with the [Logger++](https://github.com/portswigger/logger-plus-plus) module.

## Burp Dashboard Interface
The Dashboard interface is split into four quadrants
![[Pasted image 20220524064510.png]]
1. The Tasks menu allows us to define background tasks that Burp Suite will run whilst we use the application. The Pro version would also allow us to create on-demand scans. The default "Live Passive Crawl" (which automatically logs the pages we visit) will be more than suitable for our uses in this module.
2. The Event log tells us what Burp Suite is doing (e.g. starting the Proxy), as well as information about any connections that we are making through Burp.
3. The Issue Activity section is exclusive to Burp Pro. It won't give us anything using Burp Community, but in Burp Professional it would list all of the vulnerabilities found by the automated scanner. These would be ranked by severity and filterable by how sure Burp is that the component is vulnerable.
4. The Advisory section gives more information about the vulnerabilities found, as well as references and suggested remediations. These could then be exported into a report.

## Navigation
Tabs can also be popped out into separate windows should you prefer to view multiple tabs separately. This can be done by clicking "Window" in the application menu at the top of the screen, then choosing to "Detach" tabs:
![[Pasted image 20220524065252.png]]
These can be reattached in the same way.

In addition to the menu bar, Burp Suite also has keyboard shortcuts that allow quick navigation to key tabs. By default, these are:

| **Shortcut** | **Function** |
| --- | --- |
| `Ctrl + Shift + D` | Switch to the Dashboard |
| `Ctrl + Shift + T` | Switch to the Target tab |
| `Ctrl + Shift + P` | Switch to the Proxy tab |
| `Ctrl + Shift + I` | Switch to the Intruder tab |
| `Ctrl + Shift + R` | Switch to the Repeater tab |

---
## Options
![[Pasted image 20220524065803.png]]

The settings here apply globally (i.e. they control the Burp Suite application -- not just the project). That said, many of them can be overwritten in the project settings.

There are four main ***sub-sections*** of the <u>User options tab</u>:  

-  The options in the **Connections** sub-tab allow us to control how Burp makes connections to targets. For example, we can set a proxy for Burp Suite to connect through; this is very useful if we want to use Burp Suite through a network pivot.
- The **TLS** sub-tab allows us to enable and disable various TLS (**T**ransport **L**ayer **S**ecurity) options, as well as giving us a place to upload client certificates should a web app require us to use one for connections.
- An essential set of options: **Display** allows us to change how Burp Suite looks. The options here include things like changing the font and scale, as well as setting the theme for the framework (e.g. dark mode) and configuring various options to do with the rendering engine in Repeater (more on this later!).  
- The **Misc** sub-tab contains a wide variety of settings, including the keybinding table (HotKeys), which allowing us to view and alter the keyboard shortcuts used by Burp Suite. Familiarizing yourself with these settings would be advisable, as using the keybinds can speed up your workflow massively.  

With these options, we can customize our Burp install to suit our individual preferences.

---
The five main **sub-tabs** in <u>Projects options</u>

- **Connections** holds many of the same options as the equivalent section of the User options tab: these can be used to override the application-wide settings. For example, it is possible to set a proxy for just the project, overriding any proxy settings that you set in the User options tab. There are a few differences between this sub-tab and that of the User options, however. For example, the "Hostname Resolution" option (allowing you to map domains to IPs directly within Burp Suite) can be very handy -- as can the "Out-of-Scope Requests" settings, which enable  us to determine whether Burp will send requests to anything you aren't explicitly targeting (more on this later!).
- The **HTTP** sub-tab defines how Burp handles various aspects of the HTTP protocol: for example, whether it follows redirects or how to handle unusual response codes.
- **TLS** allows us to override application-wide TLS options, as well as showing us a list of public server certificates for sites that we have visited.
- The **Sessions** tab provides us with options for handling sessions. It allows us to define how Burp obtains, saves, and uses session cookies that it receives from target sites. It also allows us to define macros which we can use to automate things such as logging into web applications (giving us an instant authenticated session, assuming we have valid credentials).
- There are fewer options in the **Misc** sub-tab than in the equivalent tab for the "User options" section. Many of the options here are also only available if you have access to Burp Pro (such as those configuring Collaborator). That said, there are a couple of options related to logging and the embedded browser (which we will look at in a couple of tasks) that are well worth perusing.
---
## Introduction to Burp Proxy
The Burp Proxy is the most fundamental (and most important!) of the tools available in Burp Suite. It allows us to capture requests and responses between ourselves and our target. These can then be manipulated or sent to other tools for further processing before being allowed to continue to their destination.

For example, if we make a request to `https://tryhackme.com` through the Burp Proxy, our request will be captured and won't be allowed to continue to the TryHackMe servers until we explicitly allow it through. We can choose to do the same with the response from the server, although this isn't active by default. This ability to intercept requests ultimately means that we can take complete control over our web traffic -- an invaluable ability when it comes to testing web applications.