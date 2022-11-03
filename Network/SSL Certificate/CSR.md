#networking #SSL #TLS 
## Certificate Sigining Request
- [ ]  CSR contains **information** (e.g. common name, organization, country) the Certificate Authority (**CA**) will use to create your **certificate**
- [ ] Generated on the **same server** you plan to install the certificate on
- [ ] The CSR itself is usually created in a **Base-64** based **PEM** format
- [ ] can be generated using **terminal** similar to ssh-keygen

### What information is included in CSR
1. Information about your **business and the website** you’re trying to equip with SSL, including:
	 - **Common Name** (CN): The fully qualified **domain** name (FQDN) of your server.
	- **Organization** (O): The **legal name** of your organization. For EV and OV SSL Certificates, this information is verified by the CA and included in the certificate.
	- **Organizational Unit** (OU): The **division** of your organization handling the certificate.
	- **City/Locality** (L): The city where your organization is **located**. 
	- **State/County/Region** (S)
	- **Country** (C)
	- **Email** Address: Email address used to **contact your organization**.
2. **public key**
3. Information about the key **type** and **length**