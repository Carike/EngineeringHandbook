# Kubernetes


## Training

- [Kubernetes training](https://kubernetes.io/training/)


## Authentication

https://learn.microsoft.com/en-us/answers/questions/1468527/authentication-for-application

to add authentication to your application using Azure Active Directory and Nginx ingress controller, you can follow these general steps:

Create an Azure AD application and configure it to allow authentication for your application. You can follow the steps in this article to create an Azure AD application: Configure your App Service or Azure Functions app to use Azure AD login.
Configure your Nginx ingress controller to use Azure AD authentication. You can use the nginx-ingress-external-auth module to authenticate requests to your application. This module allows you to use an external authentication service, such as Azure AD, to authenticate requests to your application.
Configure your ingress resource to use the Nginx ingress controller and enable authentication. You can add annotations to your ingress resource to enable authentication and specify the authentication service to use. Here is an example of an ingress resource that uses the Nginx ingress controller and Azure AD authentication:
YAML

Copy
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: my-ingress
  annotations:
    nginx.ingress.kubernetes.io/auth-url: "https://login.microsoftonline.com//oauth2/v2.0/authorize?client_id=&response_type=code&redirect_uri=https:///oauth2/callback&response_mode=query&scope=openid&state="
    nginx.ingress.kubernetes.io/auth-signin: "https://login.microsoftonline.com//oauth2/v2.0/authorize?client_id=&response_type=code&redirect_uri=https:///oauth2/callback&response_mode=query&scope=openid&state="
spec:
  rules:
  - host: 
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: 
            port:
              name: http

You will need to replace <tenant-id>, <client-id>, <your-app-url>, <state>, <your-hostname>, and <your-service-name> with the appropriate values for your application.

Deploy your application and ingress resource to your Kubernetes cluster. Once deployed, you should be able to browse to your hostname and be redirected to the Microsoft login page. After authentication, you should be redirected back to your application.
Note that this is a general overview of the steps involved in adding Azure AD authentication to your application using Nginx ingress controller. The exact steps may vary depending on your specific application and environment.

## Add-ons

* https://opencost.io/
  * https://opencost.io/docs/installation/ui/
* Trivy
  * [Getting started](https://trivy.dev/latest/getting-started/)
  * [Demo](https://github.com/itaysk/trivy-demo)