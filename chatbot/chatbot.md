# Horizon Chatbot Service

Starts a web application (index.html) to connect to IBM Watson Assistant chatbot. 

Open your browser and navigate to:

http://localhost:9080

## Input Values

The following input values can be given to this service in the input file given to `hzn register`:


| Name | Required? | Type | Description |
| ---- | --------- | ---- | ---------------- |

| MOCK | no | boolean | default is false. If true, send fake data instead of querying the cpu and gps services |
| PUBLISH | no | boolean | default is true. If false, do not send data to message hub, only print it to the log |



#### Example:
A sample `services` section of the input file given to `hzn register`:
```
    "services": [
        {
            "org": "$HZN_ORG_ID",
            "url": "https://$MYDOMAIN/service-$CHATBOT_NAME",
            "versionRange": "[0.0.0,INFINITY)",
            "variables": {
                "MOCK": false,
                "PUBLISH": true,
            }
        }
    ]
```

## Deployment Values

These values can be specified in the `deployment` section of the service definition, or be overridden in the `deployment_overrides` section of your pattern.


| Name | Type | Description |
| ---- | ---- | ---------------- |
| image | string | Docker Image |


#### Example:
```
    "services": {
            "chatbot": {
                "image": "$DOCKER_HUB_ID/${ARCH}_$CHATBOT_NAME:$CHATBOT_VERSION",
                "privileged": true,
                "ports": [
                    {
                        "HostPort": "9080:9080/tcp",
                        "HostIP": "0.0.0.0"
                    }
                ]
            }
        }
```
