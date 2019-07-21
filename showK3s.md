![showK3s-logo](./images/showK3s_logo.png)

# showK3sとは

showK3sは、Cloud Native Days Tokyo 2019（CNDT2019）でのショーケース企画として新たに発足したプロジェクトです。

名前の通り、「k3s」を用いて何かできないか、というところから企画がスタートしました。

[k3s](https://k3s.io/)はRancher Labsがリリースした軽量版のk8sで、リソースの制限されたIoT等の用途に適しています。

showK3sでは、次のコンセプトで企画が準備されました。

- 会場に用意したARMボード上でクラスタを展開する

- showKsと連携して、来場者に”お持ち帰り”して貰えるものを提供する

k3s上で実行するアプリは、IoT機器の特徴を活かしつつ、来場者にお楽しみ頂けるものとしてカメラアプリを実装しました。

# showK3s構成

![showk3s-arch](./images/showk3s-arch.png)

showK3sでは、showKsと連動した画像作成を行います。

showKsで作成された画像をサーバーから取得し、カメラで撮影した映像と重ね合わせて表示します。

撮影機能で映像のスナップショットを作成・保存し、保存先URLをQRコードとして画像に付与します。

各リソースは次の機能を持ちます。

- s3-syncer
  - showKsで作成された画像を取得する
- mjpg-streamer
  - カメラで動画を撮影する
- Demo application
  - showKs画像と動画を重ね合わせる
  - 動画のスナップショットを作成し、QRコードを付与して画像をアップロードする

# 展示ブース

CNDT 2019では、showK3sのデモ展示をしています。

展示ブースではshowKsと連動した画像作成をタッチパネルでご体験頂けます。

作成した画像をその場でお持ち帰り頂くことも可能です。

また、showK3sに関しての質問も受け付けておりますので、なにかお聞きになりたいことがありましたらブース担当者までお気軽にお声がけください。

## 機器構成

Raspberry Pi 3 × 2（マスター、ノード各1台）

Raspberry Pi Camera V2 × 1

## 体験方法

![showk3s-top](./images/showk3s-top.png)

showK3sアプリのトップページです。

「撮影開始」ボタンをタップしてください。

![showk3s-stream](./images/showk3s-stream.png)

カメラ映像がshowKsの画像と重ね合わせて表示されます。

「撮影」ボタンをタップしてください。

![showk3s-snapshot](./images/showk3s-snapshot.png)

スナップショットが作成されました。

QRコードを読み取ることで画像を保存できます。

# ハッシュタグ

showKsに関しては `#CNDT2019` と `#showK3s` の2つのハッシュタグをつけてのTweetにご協力をお願いします。
たくさんの感想やご意見をお待ちしております。
