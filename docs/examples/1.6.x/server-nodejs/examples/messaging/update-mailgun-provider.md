const sdk = require('node-appwrite');

const client = new sdk.Client()
    .setEndpoint('https://cloud.appwrite.io/v1') // Your API Endpoint
    .setProject('<YOUR_PROJECT_ID>') // Your project ID
    .setKey('<YOUR_API_KEY>'); // Your secret API key

const messaging = new sdk.Messaging(client);

const result = await messaging.updateMailgunProvider(
    '<PROVIDER_ID>', // providerId
    '<NAME>', // name (optional)
    '<API_KEY>', // apiKey (optional)
    '<DOMAIN>', // domain (optional)
    false, // isEuRegion (optional)
    false, // enabled (optional)
    '<FROM_NAME>', // fromName (optional)
    'email@example.com', // fromEmail (optional)
    '<REPLY_TO_NAME>', // replyToName (optional)
    '<REPLY_TO_EMAIL>' // replyToEmail (optional)
);