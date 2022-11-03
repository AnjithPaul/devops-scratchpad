#networking #SSL #TLS 
## SSL Certificate
- [ ] authenticates a website's **identity** and enables an **encrypted** connection
- [ ] SSL stands for Secure Sockets Layer, a security **protocol** that creates an **encrypted link** between a web server and a web browser.
- [ ] website secured by SSL uses **HTTPS** instead of HTTP
- [ ] new version of SSL protocol is **TLS** (Transport Layer Security)
- [ ] certificate has a max lifespan of **27 months**. When an SSL certificate expires,  visitors will receive a **message** "This **site is not secure**. Potential risk ahead".
- [ ] the entire HTTPS encryption and decryption process is known as **SSL termination**

### SSL Handshake
1. A browser or server **attempts to connect** to a website (i.e., a web server) secured with SSL.
2.  The browser or server **requests** that the web server **identifies** itself.
3.  The web server sends the browser or server a copy of its **SSL certificate in response.**
4.  The browser or server **checks** to see whether it trusts the SSL certificate. If it does, it signals this to the webserver.
5.  The web **server** then returns a **digitally signed acknowledgment** to start an SSL encrypted **session**.
6.  **Encrypted data** is shared between the browser or server and the webserver.

### Types of SSL Certificate
1. [[EV SSL|Extended Validation certificates]]
2. [[OV SSL|Organization Validated certificates]]
3. [[DV SSL|Domain Validated certificates]]
4. [[Wildcard SSL|Wildcard SSL certificates]]
5. [[MDC|Multi-Domain SSL Certificate]]
6. [[UCC|Unified Communications Certificate]]

### How to Obtain an SSL Certificate
- [ ] cost: **free** to **hundreds** of dollars
- [ ] time: **minutes** to **a week**
- [ ] steps
	1.  Prepare by getting your **server set up** and ensuring your **WHOIS record** is updated and matches what you are submitting to the Certificate Authority (it needs to show the correct company name and address, etc.)
	2.   Generating a **Certificate Signing Request** ([[CSR]]) on your server. This is an action your hosting company can assist with.
	3.   **Submitting** this to the **Certificate Authority** to validate your domain and company details
	4.   **Installing** the certificate they provide once the process is complete.