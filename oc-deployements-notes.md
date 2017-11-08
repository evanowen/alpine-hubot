# Build
docker build -t registry.starter-us-east-2.openshift.com/luebken/alpine-hubot .

# Deploy
docker push registry.starter-us-east-2.openshift.com/luebken/alpine-hubot
oc new-app luebken/alpine-hubot -e HUBOT_SLACK_TOKEN=<HUBOT_SLACK_APP_TOKEN>

# Delete
oc delete dc alpine-hubot
oc delete svc alpine-hubot