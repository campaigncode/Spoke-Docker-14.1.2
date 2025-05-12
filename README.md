[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v1.4%20adopted-ff69b4.svg)](CODE_OF_CONDUCT.md)

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.com/template/KCfCN3?referralCode=eM55xc)

## Spoke History

Spoke is an open source text-distribution tool for organizations to mobilize supporters and members into action. Spoke allows you to upload phone numbers, customize scripts and assign volunteers to communicate with supporters while allowing organizations to manage the process.

Spoke was created by Saikat Chakrabarti and Sheena Pakanati, and is now managed by StateVoices.

The latest version is [14.1.2](https://github.com/StateVoicesNational/Spoke/blob/main/docs/RELEASE_NOTES.md) 

## Setting up Spoke

This version of Spoke can be deployed on Railway. Alternatively, the docker image can be deployed anywhere!
[Docker Image](https://hub.docker.com/r/rar1871/spoke)

Want to know more?
[Click here to visit the Spoke Documentation microsite!](https://statevoicesnational.github.io/Spoke/)

## Upgrading from an old version of Spoke

If you used the previous version of this template (13.1.0), there are a few additional steps that need to be performed to upgrade your existing installation to the new version. All organizations, campaigns, and messages from the previous version will be preserved.

Note: There will be downtime of about 10-15 minutes, during which Spoke will become inaccessible. Plan accordingly. *Do not attempt to start the new Spoke service alongside the old one to bypass this as it may corrupt your database irrecoverably.*

1. Navigate to the Railway project where Spoke is deployed. If you used the template, you should see a Spoke service and a Postgres service.
2. Click on the existing Spoke service (which may also be named Spoke 13.1.0)
    - From the `Deployments` tab, find the active deployment
    - Click the three dots on the right and select `Remove`. This will shut down the old Spoke deployment
    - Click on `Variables` tab, then the `Raw Editor` button
    - Select all text and copy it
3. In the project, right click in any empty area and from the `Add new service` dropdown, select `Empty Service`
4. Once the service is created, name it `Spoke 14.1.0`
    - Navigate to `Variables` > `Raw Editor` in the new Spoke service
    - Paste the text copied from earlier
    - Click `Update Variables`
    - Once the window closes, stay in the `Variables` tab and click `Add Variable`
    - Paste the following into the `VARIABLE_NAME` box: `DYNAMICASSIGNMENT_BATCHES="finished-replies-tz,vetted-texters,finished-replies"`. It should automatically populate the name and value boxes.
    - Click `Add`
5. In the new Spoke service, navigate to the `Settings` tab
    - Under `Source` click `Connect Repo`
    - Paste the following URL: `https://github.com/campaigncode/Spoke-Docker-14.1.2`
6. Click the purple `Deploy` button at the top of the screen. The new Spoke service should begin deploying.
7. Under the new Spoke service, navigate to `Settings`
    - Under `Networking > Public Networking`, you can add a custom domain (used to access Spoke from the internet).
    - You may also click `Generate Public Domain` to obtain a free Railway domain name. *This is not recommended*. If you were using a free Railway domain name for the old Spoke service, you will not be able to use it for the new Spoke service due to security reasons.

After completing these steps, your new Spoke service should be accessible from the URL. You can now safely delete the old Spoke service by clicking on it, going to `Settings > Delete Service` and deleting the Service.

# License

Spoke is licensed under the [GPL3 license with a special author attribution requirement](LICENSE).
