# open-horizon
IBM Open Horizon-Chatbot Example


## Building and Publishing the MMS Example for ML model updates

1. Clone this git repository:

```bash
cd ~   # or wherever you want
git clone https://github.com/jiportilla/Edge-Chatbot.git
cd ~/Edge-Chatbot/chatbot
```

2. Set the values in `horizon/hzn/json` to your liking. These variables are used in the service and MMS metadata `object.json` files. They are also used in some of the commands in this procedure. After editing `horizon/hzn.json`, set the variables in your environment:

```bash
export ARCH=amd64```

3. Build the docker image:

```bash
make build
```

For example, when using the default values provided in this demo [hnz.json](https://raw.githubusercontent.com/jiportilla/Edge-Chatbot/master/horizon/hzn.json) configuration file:

```bash
docker build -t iportilla/chatbot_amd64:1.0.0 -f ./Dockerfile.amd64 .
```
