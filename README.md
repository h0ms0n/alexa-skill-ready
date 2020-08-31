# alexa-skill-ready
To create alexa skill


## command
### init

```bash
yarn
```

### zip
```bash
zip -r ./target/alexa-sample.zip ./project
```

### deploy
```bash
aws lambda update-function-code --function-name $yourFunctionName --zip-file fileb://target/alexa-sample.zip --profile $yourProfileName --region $yourFunctionRegion
```

