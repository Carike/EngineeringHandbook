# Certificate Management

## About
Add background

## Links
* [Certificates 101](https://www.youtube.com/watch?v=nE-fBhqbUmg)
* [Extracting the certificate and keys from a .pfx file](https://www.ibm.com/docs/en/arl/9.7?topic=certification-extracting-certificate-keys-from-pfx-file)
* https://www.sslshopper.com/article-most-common-openssl-commands.html
* http://www.freekb.net/Article?id=2460

## Generating certificate and key

1. Download certifcate from provider
1. Open Linux terminal
1. Convert pfx file to PEM for K8s secret TLS
  1.  ```openssl pkcs12 -in {filename}.pfx -out {filename}.pem```
  1. Add file location e.g. `/mnt/c/workspaces/openssl/certs`
  1. Enter the password - recieved with the certificate
  1. Enter the passphrase - the same password as in the previous step.
1. Open the new PEM file created in Visual Studio Code (or similar) to view.
1. The next step is to spilt the new PEM file into two different files, a .key and .crt files.
1. Copy private key from PEM file ([certname].key).
  1. Extract the contents from ```-----BEGIN ENCRYPTED PRIVATE KEY----- to -----END ENCRYPTED PRIVATE KEY-----```
1. Copy public certificate from PEM file ([certname].crt).
  1. Extract the contents from ```-----BEGIN CERTIFICATE----- to -----END CERTIFICATE-----```
  1. If there are multiple certs, copy them all, one after the other
1. To remove the password from .key file
  1. ```openssl rsa -inform pem -in {filename}.key -out {filename}.key```
  1. Enter passphrase
  1. A message `writing RSA key` will be displayed if successful.
1. Encrypt the key using PowerShell & kubectl.
  1. Switch to your `docker-desktop`
   ```kubectl config set-context docker-desktop```
  1. Browse to the folder where the certificates are located: cd C:/Workspaces/openssl/certs - use ls to see files in the folder.
  1. Use the following command to create and encrypt the TLS secret:
   ```kubectl create secret tls new-cert --cert=D:\Workspaces\openssl\certs\DOMAIN\CERTNAME.crt --key=D:\Workspaces\openssl\certs\DOMAIN\CERTNAME.key```
  The message secret/new-cert created will be displayed in the output.
1. Confirm if the new cert was created with the name new-cert:
   ```kubectl get secret```
1. Copy the newly created values by retrieving them using (these are the values that will be copied to the Azure Portal):
   ```kubectl get secret new-cert -o yaml```
1. Log in to the Azure Portal and browse to the Key Vaults
  1. Log in to the Azure Portal and browse the Key Vault
  1. Within Secrets search for the records you would like to update (might have to click Load more)
  1. Log in to the Azure Portal and browse to the Key Vaults (scroll down far)
    1. Copy it for the following 3 Key Vaults within “Secrets“
  1. Click on the secret you wish to update.
  1. Click “New Version“ and update the following values: Secret Value, Expiration Date & Time
  1. Click “Create“
  1. Repeat the above steps for the -key


## Verify certificates
Confirm certificate has been updated
