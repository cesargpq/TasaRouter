## Approuter for BAPIs under Cloud Foundry

### Prerequisites

Install the following application:
 
https://github.com/ivanmir/flotabackend.git

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
- A destination named "flotabackend" is defined in both  manifest.yml and xs-app.json.
- Adjust the route for the AppRouter URL under the manifest.yml (pay attention to the CF landscape domain for each URL used)
- Make sure the destination "flotabackend" points to the BAPI application's URL (listed here as prerequisite).

>**WARNING**:The *destination* name is not to be mistaken with the destination service, nor the destination name you use d to address the ABAP system. You must not modify/adapt its name. It only maps the AppRouter's URL '/' to the actual BAPI application's URL while forwarding the JWT authentication generated after the user is authorized by the Cloud Platform.



### Running

Example:

```
https://flota-approuter.cfapps.us10.hana.ondemand.com/bapi
```
