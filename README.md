# 自宅のPX-MLT5PE環境でのmirakurun構築
## channels.yml, tuners.ymlの作成
この２つのファイルはISDBScannerを使用して作成する。  
[ISDBScanner](https://github.com/tsukumijima/ISDBScanner)  

自動で作成するためにISDBScanner/dockerでファイル出力を自動化しています。  
```bash
cd ISDBScanner
docker compose build
docker compose up
```
これでISDB/outfiles以下にスキャン結果を出力します。  
最後に自動でmirakurun/confに2ファイルをコピーしていますが、事前に無効チャンネルなどを設定したい場合は修正してから次を実行してください。  

## Mirakurun初期構築～実行まで
```bash
docker compose pull
docker compose run --rm -e SETUP=true mirakurun
docker compose up -d
```
