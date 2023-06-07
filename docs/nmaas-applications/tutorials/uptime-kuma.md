# Uptime Kuma

## Introduction 

[Uptime Kuma](https://github.com/louislam/uptime-kuma) is a service monitoring application which can:

- monitor the uptime of web applications
- monitor DNS changes
- monitor response times by issuing periodic pings (ICMP requests)
- monitor SSL certificate expiry 
- monitor availability of a TCP port
- monitor for presence of a particular keyword on a web page
- various other application specific monitors for PostgreSQL, MariaDB, MongoDB, etc...
- design and create status pages

## Uptime Kuma on NMaaS

Uptime Kuma on NMaaS is fully supported in two flavors:

- standalone flavor, identical with the upstream release, without any modifications.
- extended flavor which also supports API access using a [third-party API extension](https://github.com/MedAziz11/Uptime-Kuma-Web-API).

Refer to the sections below for more details regarding deployment options for the two flavors.

### Deploiying the Standalone Version of Uptime Kuma

As with any other application available in the NMaaS catalog, the deployment process for the standalone version is:

1. Subscribe your domain to the Uptime Kuma application from the `Applications` page.
2. Deploy a new instance of Uptime Kuma, providing a unique name for it.
3. Configure the application using the application configuration wizard. In the case of the standalone version, the user deploying the application is only requested to specify the required storage, with `5Gi` being the default value.
4. Wait for the deployment to be completed and directly access the newly deployed instance.
5. Upon first access, you will be asked to create the initial Uptime Kuma account. Keep in mind that multi-user support is still in its infancy in Uptime Kuma, so monitors created by one user cannot be accessed by other users.

### Deploying Uptime Kuma together with an API Server

NMaaS also offers an extended flavor of Uptime Kuma, one that comes collocated with the open-source API server implementation by [MedAziz11/Uptime-Kuma-Web-API](https://github.com/MedAziz11/Uptime-Kuma-Web-API). The deployment process for this flavor, differs somewhat from the standalone version, taking into account the additional features. The deployment steps are:

1. Subscribe your domain to the Uptime Kuma application from the `Applications` page.
2. Deploy a new instance of Uptime Kuma, providing a unique name for it.
3. Configure the application using the application deployment wizard. Make sure to check the `Enable API` checkbox.

<figure markdown>
  ![Uptime Kuma Screenshot, enabling the API](img/uptime-kuma-screenshot-01.png){ width="350" }
  <figcaption>Fig. 1: Uptime Kuma Deployment Wizard</figcaption>
</figure>

4. Enter the username and password for the default Uptime Kuma user. NMaaS will automatically initialize a new user with the specified credentials, and the first run page will be skipped once the application is deployed. The user will be able to directly login.
5. Enter the password for the API user. The API user is different from the Uptime Kuma user. The default username for the API user is `admin`. This username cannot be changed at the moment. 
6. Finish the deployment process and access the Uptime Kuma web interface and the API's OpenAPI documentation.

<figure markdown>
  ![Uptime Kuma Screenshot, viewing the access methods](img/uptime-kuma-screenshot-02.png){ width="450" }
  <figcaption>Fig. 2: Uptime Kuma Access Methods</figcaption>
</figure>

<figure markdown>
  ![Uptime Kuma Screenshot, OpenAPI](img/uptime-kuma-screenshot-03.png){ width="450" }
  <figcaption>Fig. 3: Uptime Kuma OpenAPI Explorer</figcaption>
</figure>

!!! warning
    The accounts for the Uptime Kuma web interface and the API are different. During deployment, the username and password for the Uptime Kuma web interface can be specified, along with the password for the API.

    **The default username for the API is always `admin`.**

!!! danger
    Changing the user's password from the Uptime Kuma web interface after the application has been deployed will make the API addon nonfunctional. Contact the NMaaS team in case a password change is necessary.