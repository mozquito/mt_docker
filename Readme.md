# README

[メンテナンスし辛いMovableTypeをHeadlessCMSとして使えるようにAWS DynamoDB, S3を使って改修する](https://zenn.dev/articles/93a1aab214108c)
で使うDocker環境の雛形です。


手元にMovableTypeがない場合は[MovableType開発者登録をして開発者用ライセンスを取得し](https://www.sixapart.jp/inquiry/movabletype/developer.html)、MovableTypeをダウンロードする必要があります。
MT6.系のダウンロードするには別途申請が必要なことがあります。
商業利用する場合は別途有償ライセンスが必要です。

ダウンロードしたMovable Typeをmtにリネームし./docker/movabletypeにディレクトリごと移動します。
移動したあとにディレクトリ直下にあるmt-config.cgiを./docker/movabletype/mtに移動させます。

docker-compose.ymlのあるディレクトリに戻り

'''
docker-compose up 
'''
とするとMovableTypeが起動します。