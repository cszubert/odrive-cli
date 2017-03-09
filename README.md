# odrive-cli
Runs odrive Sync Agent CLI in an official python based docker container.
## Usage
### Start odrive container
```
docker run --rm --name odrive-cli -v $PWD:/odrive cszubert/odrive-cli
```
Next enter the container from anothe shell
```
docker exec -it odrive-cli bash
```
### Example odrive Sync Agent commands
Get odrive Synch Agent help
```
$HOME/.odrive-agent/bin/odrive -h
```
Get odrive Synch Agent status
```
$HOME/.odrive-agent/bin/odrive status
```
Authenticate odrive Synch Agent - specify the AUTH_KEY for your odrive accoount
```
$HOME/.odrive-agent/bin/odrive authenticate AUTH_KEY
```
Mount contianer path to odrive cloud path. 
The below command maps the container path /odrive (which can also be mapped to the hosts folder, as with the docker run command above), to root folder on odrive (which includes all odrive contents).
```
$HOME/.odrive-agent/bin/odrive mount /odrive /
```
Start syncing odrive cloud folder or file to container.
The below command starts synching the Google Drive foler on odrive to the container. Note that this command is not recursive and you have to start synching each file and folder that you want odrive Synch Agent to continue to sync.
```
$HOME/.odrive-agent/bin/odrive sync /odrive/Google\ Drive.cloudf
```
Refresh folder.
The below command refreshes the Google Drive folder.
```
$HOME/.odrive-agent/bin/odrive refresh /odrive/Google\ Drive
```
### Stop odrive container
```
docker stop odrive-cli
```
## More Information
odrive Sync Agent: https://odrive.readme.io/v1.0/docs/odrive-sync-agent
