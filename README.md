# alexa-skill-ready
To create alexa skill

## 事前準備
### 以下のライブラリを事前にローカルにインストールしてください
- yarn or npm
- （任意）AWS CLI（手動でもzipファイルをLambdaへアップロード可能）

## コマンド
### まずやること
```bash
yarn
```
or 
```bash
npm install
```

### zip圧縮
```bash
zip -r ./target/alexa-sample.zip *.js node_modules
```

### コマンドでLambdaへdeploy(任意)
```bash
aws lambda update-function-code --function-name $yourFunctionName --zip-file fileb://target/alexa-sample.zip --profile $yourProfileName --region $yourFunctionRegion
```
- yourFunctionName: Lambdaの関数の名前
- yourProfileName: Credentialの名前
- yourFunctionRegion: Lambdaのデプロイ先のリージョン

## Lambda環境の構築手順
1. AWSマネジメントコンソールにログイン、検索窓からLambdaを選択し開く（料金について今回のアプリで使用する分は無料枠で十分足りる）
2. Lambda関数を新規作成する、関数名は好きな名前で良いがzipファイルの名前と同じにしておく必要があるためalexa-sampleとする
3. ローカル内で作成したzipファイルをLambdaにアップロード
4. LambdaのトリガーにAlexa Skills Kitを設定
5. testを実行し、レスポンスがSuccessになれば成功
