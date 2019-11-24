## Approuter for BAPIs under Cloud Foundry

### Prerequisites

Install the following application:
 
https://github.com/ivanmir/cct-ts-connector.git

> You should have the above app's services already installed/configured before deploying the AppRouter

## Installation

### Clone the git repository
- Clone App to a folder with your preferred Git Client.

### Build
- Run the following npm commands:

```
    npm config set @sap:registry https://npm.sap.com
    npm install
```

### Deploy to Cloud Foundry
- Goto your local application folder (C:\...) and type:

```
    C:\...> cf push
```
> Manifest file should automatically be used!

### Routes
- A destination named "cct-ts-connector" is defined in both  manifest.yml and xs-app.json
- Adjust the routes for the application under the manifest.yml (pay attention to the CF landscape domain for each URL used). Make sure the destination points to the BAPI application's URL (pre-requisite).

| WARNING: This destination is not to be mistaken with the destination used by the BAPI application and shouldn't be modified/adapted. |
|It only maps the router's url '/' to the actual BAPI application's url while forwarding the JWT authentication genereated after the user is authorized by the Cloud Platform.| 
| --- |

### Running

Example:

```
https://cct-approuter.cfapps.us10.hana.ondemand.com/bapi
```
