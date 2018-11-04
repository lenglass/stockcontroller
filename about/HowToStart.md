# 概要

何もない状態から、コードのコミット、ビルド、デバッグができるようになるまでの手順を全部書いておく。何かに気づくたびに増やしていく。

## 実行環境

### 概要

iPhone ⇔ JavaScript ⇔ インターネット ⇔ Tomcat ⇔ Java ⇔ MySQL

↑ 今回の環境の全体像。これのうち、インターネットの右側を作る。

### インストール

インストールするのは git, Docker Toolbox, DockerImage(Tomcat, MySQL)の４つ

1. git  
   [ダウンロード](https://gitforwindows.org/),
   [設定](https://qiita.com/toshi-click/items/dcf3dd48fdc74c91b409)

1. Docker Toolbox  
   [ダウンロード](https://docs.docker.com/toolbox/overview/)  
   設定などはデフォルトで OK  
   ただし、「git for windows」は上の手順でインストール済みなのでチェックを外す  
   Windows(32bit)だったら[こんな手順](https://www.niandc.co.jp/sol/tech/date20180316_1645.php)が必要らしい  
   うまく volume を mount できないときの[設定](https://qiita.com/dojineko/items/f623894ef2436bef890e)（困ってなければ対応不要。vboxmanage はたぶんパス通ってないから、代わりに GUI で[こんな感じ](http://pineplanter.moo.jp/non-it-salaryman/2016/10/19/virtualbox-share-folder/)の画面操作で）

1. Docker Image の設定  
   イメージをつかむために、最初に[この連載](https://knowledge.sakura.ad.jp/13265/)を読んでおくといいかも。

   1. MySQL のイメージファイルの作成  
      [参考](https://qiita.com/astrsk_hori/items/e3d6c237d68be1a6f548)

   1. Tomcat のイメージファイルの作成  
      [参考](http://mabushiisign.hatenablog.jp/entry/2018/03/17/011829)

## 開発環境

### 用語

- バージョン管理（git）  
   [詳細](https://backlog.com/ja/git-tutorial/intro/intro1_1.html)

### 作成しておくアカウント

- GitHub アカウントを作成  
  https://github.com/

- ATLASSIAN アカウントを作成  
  https://id.atlassian.com/signup

### インストール

- IntelliJ IDEA Community（統合開発環境）  
  [ダウンロード](https://www.jetbrains.com/idea/)

- SourceTree（バージョン管理ツール）  
  [ダウンロード](https://ja.atlassian.com/software/sourcetree)  
  [noreply 設定](http://ryoichi0102.hatenablog.com/entry/2017/10/12/000713)も一応しておいた。

## 最初のコミットまで

### ファイルの入手

1. SourceTree を起動
1. Clone を選択
   - 元のパス https://github.com/lenglass/stockcontroller
   - 保存先のパス （適当に選ぶ。デフォルトでも OK）
1. クローン をクリック

### ファイルのコミット

1. 作業ツリーのファイル、から保存したいファイルを選んで「選択をインデックスに追加」を選択
1. 保存したいファイルを全部追加できたら、下の枠に一言何をやったか書く
1. 「変更をすぐに origin/master にプッシュする」のチェックボックスにチェックを入れて、右下の「コミット」をクリック

### プルリクエスト

（いつか書く）

### サーバー環境での実行

（いつか書く）

サンドボックスサーバーと正式サーバーの２つを用意する予定。
ここへはサンドボックスへの転送方法を書く。
正式サーバーは github の更新時に自動でデプロイする仕組みにしておきたい。
