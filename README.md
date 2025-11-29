# 自宅のPX-MLT5PE環境でのmirakurun構築
## channels.yml, tuners.ymlの作成
この２つのファイルはISDBScannerを使用して作成するのが良さそう。  
[ISDBScanner](https://github.com/tsukumijima/ISDBScanner)  

使用するのに[recisdb-rs](https://github.com/kazuki0824/recisdb-rs)が必要なのでこれをいれて実行する。  
面倒なのでこのあたり一括でDockerで実行してファイル出力だけやらせるように準備しておくつもりだけど後回し。  

## 初期構築～実行まで
```bash
docker compose pull
docker compose run --rm -e SETUP=true mirakurun
docker compose up -d
```
