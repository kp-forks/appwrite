<?php

use Appwrite\Client;
use Appwrite\Services\Avatars;

$client = (new Client())
    ->setEndpoint('https://<REGION>.cloud.appwrite.io/v1') // Your API Endpoint
    ->setProject('<YOUR_PROJECT_ID>') // Your project ID
    ->setSession(''); // The user session to authenticate with

$avatars = new Avatars($client);

$result = $avatars->getQR(
    text: '<TEXT>',
    size: 1, // optional
    margin: 0, // optional
    download: false // optional
);