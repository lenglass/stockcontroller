# stockcontroller

在庫管理システム

![overview image](https://github.com/lenglass/stockcontroller/blob/master/about/overview.png?raw=true)

```mermaid
sequenceDiagram
iPhone ->> サーバ: 在庫データ送信
サーバ ->> データベース: 在庫データ更新
データベース ->> サーバ: 更新後の在庫データ
サーバ ->> iPhone: 更新後の在庫データ返信
```
