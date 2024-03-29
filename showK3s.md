# showK3sとは

Cloud Native Days Tokyo 2019（CNDT2019）でのショーケース企画として、新たに発足したプロジェクトです。

showK3sという名前の通り、「k3s」を用いて何かできないか、というところから企画がスタートしました。

[k3s](https://k3s.io/)はRancher Labsがリリースした軽量版のk8sです。  
リソースの制限された環境での動作に適しており、IoT機器を使用したエッジコンピューティング等の分野で注目を集めています。

showK3sでは、次のコンセプトで企画が準備されました。

- 会場に用意したARMボード上でk3sクラスタを展開する
- showKsと連携して動作する
- 来場者がその場で体験し、”お持ち帰り”して貰えるものを提供する

k3s上で実行するアプリは、IoT機器の特徴を活かしつつ、体験される全ての人がイメージしやすいものとしてカメラアプリを実装しました。

# showK3s構成

![showk3s-arch](./images/showk3s-arch.png)

showK3sでは、showKsと連携した画像作成を行います。

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

展示ブースでは、showK3sアプリの画像作成をご体験頂けます。  
作成した画像はその場でお持ち帰り可能です。

## 機器構成

- Raspberry Pi 3 × 2（マスター、ノード各1台）

- Raspberry Pi Camera V2 × 1

## 体験方法

![showk3s-top](./images/showk3s-top.png)

showK3sアプリのトップページです。  
トップページではデモ動画を配信しています。

「撮影開始」ボタンを押してください。

![showk3s-stream](./images/showk3s-stream.png)

カメラ映像がshowKsの画像と重ね合わせて表示されます。

「撮影」ボタンを押してください。

![showk3s-snapshot](./images/showk3s-snapshot.png)

スナップショットが作成されました。  
右下のQRコードを読み取ることで画像を保存できます。

# ハッシュタグ

showKsに関しては `#CNDT2019` と `#showK3s` の2つのハッシュタグをつけてのTweetにご協力をお願いします。  
たくさんの感想やご意見をお待ちしております。
