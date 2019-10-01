# ZapSecurityTesting

1. Setting ZAP local proxy
2. Generating & Saving Root CA Certificate
3. Configure CA Certificate in Firefox
4. Configure Proxy in Firefox
4. Testing ZAP Proxy Configuration



Installation and configuration of ZAP:
# Setting up your ZAP Environment
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



# Generating a Report:
ZAP tool -> Report -> Generate HTML report (Any other options listed) -> Save and share the report.

ZAP tool -> Report -> Generate HTML report (Any other options listed) -> Save and share the report.

Authentication , session and User management using ZAP
1) Context: Represents a Web application
2) Session Management Method: How are the web Sessions identified by the server and handle requests

Example: cookie based using query parameters
3) Authentication Method: How is a new session established?
It could be either Form based authentication method, HTTP based or oath methods.
4) User Management: Handling users of web application that could be used for executing actions
Example: user name/password pair
