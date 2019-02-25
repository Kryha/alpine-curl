An alpine base minimal size docker image for curl-ing stuff.

E.g. usage: 

```
docker run DOCKERwithFILE cat file.txt|docker run -i kryha/alpine-curl -X POST -F "file=@-;filename=newname.txt" -H "Authorization: Bearer $SLACK_LICENSE_BOT" -F channels=yourchannel https://slack.com/api/files.upload
```

This will cat a file in another container and pipe its content to the curl docker. As the pipe sends a stream of data, you should specify the filetype in the curl request to get proper file parsing in slack. The example will upload this file to your desired channel.

We found this to be quite useful in CI/CD pipelines.
