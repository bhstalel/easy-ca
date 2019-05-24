This BASH script is for automating the tutorial of setting up an own CA from this [link](https://pki-tutorial.readthedocs.io/en/latest/simple/index.html) 



**HOW TO USE**

1. Clone this repository 

```
sudo git clone https://github.com/bhstalel/easy-ca.git
cd easy-ca
```

Feel free to edit the SSL Certificate request's infos in the two files :

- Root-ca.conf
- Signing-ca.conf 
```
[ ca_dn ]

0.domainComponent       = "tn"

1.domainComponent       = "talel"

organizationName        = "talel Inc"

organizationalUnitName  = "talel Inc CA"

commonName              = "talel Inc CA"
```

2. Run the CA script **(Root is required to use the script)**

* **help**
```
sudo bash ca help
```
![..](https://i.imgur.com/Yd6SoEF.png)

* **install ./newca**
```
sudo bash ca install ./newca
```
![..](https://i.imgur.com/q7OfVE9.png)

* **req FQDN**
```
sudo bash ca req www.talel.com
```
![..](https://i.imgur.com/7Crm03L.png)

All informations are **optionnal** in the **Server.conf** file, you can adjust that to **mutch**
All new generated files (key, crt, csr), will be located into: **PATH/certs/**

![...](https://i.imgur.com/21V4tzj.png)

**NOTE**

You have to import the signing-ca.crt file into your browser to make the new created CRT request'CA known by the browser

For an example of use with HTTP apache2 website into mozilla firefox , see the youtube tuto : [Youtube-link](https://www.youtube.com/watch?v=TWwyQ5x780o)
