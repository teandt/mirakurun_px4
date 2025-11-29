# 最終的な実行環境を構築します
FROM ubuntu:24.04

WORKDIR /app

# 実行に必要なパッケージと、コンパイル済みのrecisdbをインストールします
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        ca-certificates \
        pcscd \
        libpcsclite1 \
        libccid \
        curl \
        # .deb パッケージのインストールに必要
        gdebi-core && \
    # recisdb の .deb パッケージをダウンロード
    curl -sL https://github.com/kazuki0824/recisdb-rs/releases/download/1.2.3/recisdb_1.2.3-1_amd64.deb -o recisdb.deb && \
    # .deb パッケージをインストール
    gdebi -n recisdb.deb && \
    # ISDBScanner の実行バイナリをダウンロードし、実行権限を付与
    curl -sL https://github.com/tsukumijima/ISDBScanner/releases/download/v1.3.2/isdb-scanner -o /usr/local/bin/isdb-scanner && \
    chmod +x /usr/local/bin/isdb-scanner && \
    # 後片付け
    rm recisdb.deb && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# コンテナ起動時のデフォルトコマンド
CMD [ "isdb-scanner" ]
