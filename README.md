# Vault-UI
[![](https://images.microbadger.com/badges/image/djenriquez/vault-ui.svg)](https://microbadger.com/images/djenriquez/vault-ui)
[![Run Status](https://api.shippable.com/projects/581a2fc51ae1890f00d3dd6c/badge?branch=master)](https://app.shippable.com/projects/581a2fc51ae1890f00d3dd6c)

A beautiful way to manage your secrets in Vault
![Landing Page](images/Landing.jpg)

![Secrets Management](images/Secrets.png)
![New Secrets](images/NewSecret.png)

# Configuration
Configuration is accessed by clicking on the configuration cog on the login page.
![Configuration](images/Config.png)
## Vault Endpoint
Users can enter in the full endpoint to Vault, including scheme.
## Authentication
There are currently three supported authentication backends. [Github](https://www.vaultproject.io/docs/auth/github.html), [Username and Password](https://www.vaultproject.io/docs/auth/userpass.html), and [Token](https://www.vaultproject.io/docs/auth/token.html). 
![Auth Backend](images/AuthConfig.png)

## Secrets
Secrets will be saved under the root key `value`. Secrets displayed will the value displayed for this key. For example:
If you write a value "world" to the secret key "hello", Vault will store this as `{ "value": "world" }` to the key `secret/hello`. Keys are also read by searching the key `value` in the JSON object returned by the HTTP GET for that secret.

## Policies
Policies can be entered in as JSON or as HCL. If entered in as HCL, it will be converted to JSON as required for the PUT command in Vault's API. However, existing policies that are in HCL will continue to be displayed in HCL.

# Run
Vault-UI is attached to an automated build on Docker Hub. To run Vault-UI:
```bash
docker run -d \
-p 8000:8000 \
--name vault-ui \
djenriquez/vault-ui
```

# Licensing
Vault-UI is licensed under BSD 2-Clause. See [LICENSE](https://github.com/djenriquez/vault-ui/blob/master/LICENSE) for the full license text.