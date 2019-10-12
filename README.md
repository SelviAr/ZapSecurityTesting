FO 
Security Testing Pathway -https://katrinatester.blogspot.com/2015/09/security-testing-pathway.html


# ZapSecurityTesting

## One Time Setup in the new laptop 
1. Setup ZAP Testing Environment 
2. Generate CA Certificate
3. Install CA Certificate in browser


## PreTest Setup
1. Configure Proxy setting in the browser
2. Configure ZAP Proxy for testing
*  Set No of instance
* Set deep level

## Security Testing
1. Web Session capture
2. Context Setting
4. Set Auth TYpe
3. Add User
* Set active session

3. Spidering
4. AJAX Spidering
5. Active Scanning


## PostTest 
1. Generate Report


# Setup ZAP Testing Environment
* **JAVA SDK:** - [How to Install the Java Software Development Kit](https://www.wikihow.com/Install-the-Java-Software-Development-Kit)
* **ZAP Prozy Tool** -
  * Download ZAP installer - https://github.com/zaproxy/zaproxy/wiki/Downloads


# Starting OWASP ZAP
```bat
Option:1
Go to ZAP Folder and open the tool. Example: C:\Program Files\OWASP\Zed Attack Proxy\ZAP.exe

Option:2
From command prompt, java -Xmx512m -jar zap-2.7.0.jar
```

# Generating & Saving Root CA Certificate
Once ZAP Opened - [Generate CA Certificate](https://www.youtube.com/watch?v=Uin07SHkQTE)
* [Adding SSL Certificates from OWASP ZAP - A Visual Walkthrough](https://2buntu.com/articles/1517/adding-ssl-certificates-from-owasp-zap-a-visual-walkthrough/)
* Go to Tools>Options>Dynamic SSL Certificate. Click Generate and then click Save.
* Save the certificate in the desired location.
* Open your browser and install the Certificate to your browser (Firefox, Chrome, IE) accordingly 
![](https://i.stack.imgur.com/cqqcH.png)

# Configure CA Certificate 
Browser Options
Tab Advanced
Tab Cryptography/Certificates
Click View certificates
Click tab Trusted root certificates
Click Import and choose the saved owasp_zap_root_ca.cer file


# Zap runs on proxy, to set up the proxy in ZAP
* ZAP tool -> Tools Menu -> Options -> Local Proxy -> Note down IP Address, it could be 127.0.0.1 Port = 8080.


# Manually Configure Explicit Proxy Settings in the Browser
* Go to IE browser -> Tools Menu -> Options -> Advanced tab -> Network -> Settings -> Select Manual Proxy configuration:- HTTP Proxy = 127.0.0.1 Port = 8080

[How to set a proxy server in Chrome, Firefox, Internet Explorer, Microsoft Edge and Opera](https://www.digitalcitizen.life/how-set-proxy-server-all-major-internet-browsers-windows)

Ensure web traffic is captured. 

## Security Testing
1. Web Session capture
View-> Show all tab


At left pane, select the website that you are testing and include in Context as shown below.
https://224926-685269-raikfcquaxqncofqfm.stackpathdns.com/wp-content/uploads/2017/02/img_58a2b2b112943-600x127.png
https://224926-685269-raikfcquaxqncofqfm.stackpathdns.com/wp-content/uploads/2017/02/img_58a2b2f79397c-600x465.png

Then, find your login page’s POST request and right click and add a Form-based Auth Login Request as shown below.
Flag as Context –> Default Context: Form-based Auth Login Request

https://224926-685269-raikfcquaxqncofqfm.stackpathdns.com/wp-content/uploads/2017/02/img_58a2b4175d477-768x165.png

Then, ZAP automatically fills “Login Request POST Data” after that you have to select username and password parameters by using dropdown values.

https://224926-685269-raikfcquaxqncofqfm.stackpathdns.com/wp-content/uploads/2017/02/img_58a2b61201f45-1024x508.png

And then, click “Users” and add a user.
https://224926-685269-raikfcquaxqncofqfm.stackpathdns.com/wp-content/uploads/2017/02/img_58a2b68daa4b6-1024x508.png
And for “Regex pattern identified in Logged in response messages” part, you need to check your login response and select a significant part that shows that we logged in such as “click to logout”.

https://224926-685269-raikfcquaxqncofqfm.stackpathdns.com/wp-content/uploads/2017/02/img_58a2b7f2a5eb5-1024x305.png

Then, ZAP automatically sets logged in response message part.

https://224926-685269-raikfcquaxqncofqfm.stackpathdns.com/wp-content/uploads/2017/02/img_58a2b84a203ce-1024x223.png


https://www.swtestacademy.com/zap-authentication/

[Authentication in ZAP](https://www.swtestacademy.com/zap-authentication/)

2. Context Setting
4. Set Auth TYpe
3. Add User
* Set active session



# Generating a Report:

ZAP tool -> Report -> Generate HTML report (Any other options listed) -> Save and share the report.

Authentication , session and User management using ZAP
1) Context: Represents a Web application
2) Session Management Method: How are the web Sessions identified by the server and handle requests

Example: cookie based using query parameters
3) Authentication Method: How is a new session established?
It could be either Form based authentication method, HTTP based or oath methods.
4) User Management: Handling users of web application that could be used for executing actions
Example: user name/password pair


# Practie Site
http://hack-yourself-first.com/

How does it work?
ZAP creates a proxy server and makes your website traffic pass through that server. It comprises of auto scanners that help you intercept the vulnerabilities in your website.
![](https://www.srijan.net/hs-fs/hubfs/Workflows.jpg?width=528&name=Workflows.jpg)
![](https://blog.codecentric.de/files/2013/10/overview.png)
