

# ZapSecurityTesting

## One Time Setup
1. Setup ZAP Environment
2. Generating & Saving Root CA Certificate
3. Configure CA Certificate 

## PreTest Setup
1. Configure Proxy in the browser
2. Testing ZAP Proxy Configuration

## Security Testing
1. Web Session capture
2. Context Setting
3. Spidering
4. AJAX Spidering
5. Active Scanning


## PostTest 
1. Generate Report



# Setup ZAP Environment
* JAVA 8+ : In order to install ZAP you need to install JAVA 8+ to your Windows or Linux system. If you use the Mac OS you don’t need JAVA as it’s already installed. Go to https://java.com/en/download/ and install it.
* Installer: Download ZAP installer according to your OS 
https://github.com/zaproxy/zaproxy/wiki/Downloads


# Starting OWASP ZAP
```bat
C:\Program Files\OWASP\Zed Attack Proxy\ZAP.exe
alternatively , java -Xmx512m -jar zap-2.7.0.jar
```

# Zap runs on proxy, to set up the proxy in ZAP
* ZAP tool -> Tools Menu -> Options -> Local Proxy -> Change Address = 127.0.0.1 Port = 8080.
* browser -> Tools Menu -> Options -> Advanced tab -> Network -> Settings -> Select Manual Proxy configuration:- HTTP Proxy = 127.0.0.1 Port = 8080

# Generating & Saving Root CA Certificate
Open up OWASP ZAP, go to Tools -> Options

In the Dynamic SSL Certificates*, click on Generate if you don't see a certificate, else, Save the certificate in some location comfortable to you like your home folder.

https://i.stack.imgur.com/cqqcH.png

# Configure CA Certificate 
Browser Options
Tab Advanced
Tab Cryptography/Certificates
Click View certificates
Click tab Trusted root certificates
Click Import and choose the saved owasp_zap_root_ca.cer file

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




How does it work?
ZAP creates a proxy server and makes your website traffic pass through that server. It comprises of auto scanners that help you intercept the vulnerabilities in your website.
![](https://www.srijan.net/hs-fs/hubfs/Workflows.jpg?width=528&name=Workflows.jpg)
![](https://blog.codecentric.de/files/2013/10/overview.png)
