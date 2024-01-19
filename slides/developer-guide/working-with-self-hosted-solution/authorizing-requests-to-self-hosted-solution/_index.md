---
title: "Authorizing Requests to Self-Hosted Solution"
type: docs
url: /authorizing-requests-to-self-hosted-solution/
weight: 40
---

By default (when ClientId and ClientSecret are not specified) the requests are not authorized, so anyone who has access to the container has access to the API hosted there.

You may specify ClientId and ClientSecret invented by you as environment parameters for the container (not to be mixed with license public & private keys that you get from Aspose).

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key"\
-e "ClientId=MyClientId" -e "ClientSecret=MyClientSecret"\
-v "/data:/storage" aspose/slides-cloud
```

When you start the container with ClientId and ClientSecret set, you must get auth token using /connect/token URL before making API requests.

```sh
curl -X POST "http://localhost:8088/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret"
```

Then you provide the token in the Authorizatrion header for API requests just the way you authenticate cloud requests at api.aspose.cloud. For example,

```JAVA
curl -X POST "http://localhost:8088/v3.0/slides/convert/pdf" --data-binary "@presentation.pptx" -H "Content-Type: application/octet-stream" -o "presentation.pdf" -H "Authorization: Bearer <token>"
```