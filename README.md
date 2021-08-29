# Dialogflow CX WhatsApp Integration with Twilio

A simple way to connect and integrate Dialogflow CX with Whatsapp with Twilio. 


## DialogflowCX and Cloud function configuration


**1.** Open you Dialogflow CX console ([here](https://dialogflow.cloud.google.com/cx/projects)) and select the your project and create your agent. If you already have one, don't worry about this step.

**2.** Open the Google Console for Cloud Functions ([here](https://console.cloud.google.com/functions)) and make sure you have the Google Project of your Dialogflow CX selected.

**3.** Click on "Create Function" to open the interface for function creation.

**4.** Set the name of the function.

**5.** On the **Source Code** option, select **Inline Editor** .

**6.** In the **index.js** tab, copy and paste the code from the index.js file in this repository.

**7.** In the **package.json** tab, copy and paste the code from the package.json file in this repository.

**8.** Set the **Function to Execute** field to the name set in Step 2.

**9.** Click on the Dropdown "**Runtime, Build, Connections and Security Settings**"

**10.** In the **Enviroment Variables** section, look for **Runtime Enviroment Variables** and click on "Add Variable"

**11.** From the DialogflowCX dashboard select the project and from the hamburger menu on the left copy the name. For e.g.
`projects/PROJECT_ID/locations/LOCATION/agents/AGENT_ID`

**12.** Copy and add the variables called:

- **accountSid** The Account SID is given on the console of Twilio account. Refer to instruction 12 for more info.

- **authToken** The authentication token for your Twilio acconut, is given on the console of your Twilio project. Refer to instruction 12 for more info

- **projectId** This can be found after `project/` from thr URL copied above.

- **agentId** This can be found after `agents/` from thr URL copied above.

- **location** This can be found after `locations/` from thr URL copied above.

- **languageCode** This can be found on Dialogflow CX dashboard. For e.g for English it will be `en`

**13.** To deploy the funciton you need to enable the Cloud Build API, you can find it here [here](https://console.cloud.google.com/marketplace/product/google/cloudbuild.googleapis.com)

**14.** Allow you cloud function for public access. Here are the steps [here](https://cloud.google.com/functions/docs/securing/managing-access-iam)

**15.** Click on your created function. Open the **Trigger** tab and copy the trigger URL.

## Twilio configuration

**16.** Create your free account in Twilio and from the console copy `accountSid` and `auth_token` which will be used as enviroment variables in cloud function.

**17.** From the left menu select **messaging** and from **Try it out** select **Send a Whatsapp message**. This should open Twilio Sandblox for Whatsapp.

**18.** In your Twilio Sandbox configuration ([link](https://www.twilio.com/console/sms/whatsapp/sandbox)), paste the URL into the "**when a message comes in**" field and click **save** and follow the instructions.

**19.** You can now test the integration of your Dialogflow CX agent with the Twilio Sandbox's WhatsApp number.
