mbed Device Connector integration bridge image importer for Google Cloud PubSub 

Original Date: January 26, 2017

4/26/2017: Updated with the latest bridge (patches for R1.2 GA)

1/26/2017: Initial checkin

Container Bridge source (Apache 2.0 licensed - Enjoy!): https://github.com/ARMmbed/connector-bridge.git

Container Bridge Instance Installation:

1). Clone this repo into a Linux instance that supports docker images

2). cd into the cloned repo and run: ./run-reload-bridge.sh


If Starting on a Docker instance: 

3). Note the public IP address of your linux runtime - update "start-bridge.sh" and replace "192.168.1.230" with yours

4). invoke: ./start-bridge.sh

Once the container instance is live, you must configure the bridge and bind it between your mbed Connector account and your PubSub Service in Google Cloud

1). In Google Cloud, create your project... your project will be named.  Save this name

2). Create a PubSub instance in your project - enable the PubSub API.

3). In Google Cloud IAM, create a service account and authentication JSON for project. This will be your "IAM credential JSON"

4). Next go to https://connector.mbed.com and create your mbed Connector Account

5). Once your Connector account is created, you need to "Access Keys" to create a Connector API Key/Token. Record the Token Value

Now that you have your:

    - Google Cloud Project Name. Enter this as your "google_cloud_application_name" value

    - Google Cloud Project IAM credential JSON. Enter this as your "google_cloud_auth_json" value

    - Connector API Key/Token generated

Go to:  https://[[your containers public IP address]]:8234

    - username: "admin" (no quotes)

    - password: "admin" (no quotes)

Enter each of application name value, auth json value, and Connector API Token

    - Please press "SAVE" after *each* is entered... 

    - Once entered, press "Restart" to restart the bridge

Your GoogleCloud-Connector bridge should now be configured and operational. 

For your mbed endpoint, you can clone and build (via mbed-cli) this: https://github.com/ARMmbed/mbed-ethernet-sample-withdm

    - This sample assumes you are using the NXP K64F + mbed Application Shield

Additionally, a Google Cloud PubSub example has been published here:

    - https://github.com/ARMmbed/GoogleCloudConnectorExerciser

This sample provide an example on how, from within Google Cloud, you can read and react to events and telemetry via the bridge.

Enjoy!

Copyright 2017. ARM Ltd. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License. 
