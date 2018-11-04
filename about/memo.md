# 環境選定

ツール・サービスを選んだ理由を書き残す
細かなツールは下の環境構築欄に

## git ホスティングサービス

プライベートリポジトリにするかどうか、がかなり迷いどころ。  
 今回は、どうせ俺がコミッターになるからパブリックで作ろう。  
 問題あれば BitBucket/GitLab に移行する、ってことで。  
 git クライアントに SourceTree を使うので、プライベートにするなら BitBucket に移行する予定。

## git クライアント

GUI 必須。ということで評判のよい SourceTree で決まり。

## データベース

mysql
特に考えなし。無料だし学習コスト安いしいいかなって。

## 仮想コンテナ

誰のパソコンでもサーバーと同じ環境を作れるようにしておけば、デバッグが簡単になる。  
 あといざって時にサーバの引っ越しがらくちん。  
 このあたりから仮想コンテナを使うことにした。  
 導入も普通に各ソフトインストールするより、導入済みコンテナもらってきたほうが楽そうだし。  
 使うのは Docker、これはもうデファクトスタンダードってことでいいよね。  
 kubernetes は今回の用途だと要らん気がするから導入未検討。

## サーバー

サーバーサイド Java を無料で使いたい。  
 それなりになんとかなりそうなのは Google Cloud Platform（３万円枠がもらえるから、多少はみ出してもアラートで止めれば問題なしにできる）
http://uphy.hatenablog.com/entry/2017/07/22/192352

## サーバーサイド Java

Tomcat が要るね。

## Java フレームワーク

Spring でいってみるか。デファクトスタンダードなら知っておいて損はないでしょ。
Spring Boot が今かなりよさそう。Spring Framework からかなり簡略になってるぽい。

# 環境構築

環境を作成するためにやったこと  
設定値などもここに

## google cloud platform

https://qiita.com/ndxbn/items/7ef0a96e409a5b5837bd
この辺の手順に従ってやった
https://blog.apar.jp/web/6966/

## ssh クライアント

業界標準な気がする PeTTY（パティ）をインストール
http://hp.vector.co.jp/authors/VA024651/PuTTYkj.html
↓ はうまく解凍できなかったので使っていない
https://www.ranvis.com/putty

## Docker

Docker Toolbox
Windows 10 pro 以外では Docker for windows が使えないので。
https://docs.docker.com/toolbox/overview/#whats-in-the-box

以下のような設定を以前したはずだけど、今見たらファイルが空になっていた。
もし volume の mount がうまくできない場合は、この辺も見直すといいかも。
docker-machine ssh
vi /var/lib/boot2docker/bootlocal.sh
mkdir -p /d/Master
mount -t vboxsf -o defaults,iocharset=utf8,uid=1000,gid=50 d/Master /d/Master

## git

後で細かくインストールするのだるいので
https://qiita.com/toshi-click/items/dcf3dd48fdc74c91b409

## tomcat

https://hacknote.jp/archives/20181/
alpine, tomcat, mysql_jdbc は現時点での最新版を選択
jdk は alpine に jdk8 までしかなかったので、そのままで

## Spring Boot

https://qiita.com/akiraabe/items/0ae812eb3a5b2288da3a

## eclipse

総学習コストを下げるため、IntelliJ は見送り。
eclipse のプロジェクトファイルはバージョン管理しない。
（どれが必要かようわからん！）

# 後で使うかも

## Docker

[docker で volume をマウントしたときのファイルの owner 問題](https://qiita.com/yohm/items/047b2e68d008ebb0f001)
