# Azure Functiosn の作成

## 概要

この演習では、Azure Functions アプリケーションを作成する方法を学びます。この演習では、Java で作成された Azure Functions アプリケーションを使用します。

## 作業手順

### Task 1 - リソースグループの作成

- リソースグループ名： functions-hands-on
- リージョン： West US

<img src="../images/ex1/1-01.png" width="800" />
<img src="../images/ex1/1-02.png" width="800" />
<img src="../images/ex1/1-03.png" width="800" />
<img src="../images/ex1/1-04.png" width="800" />
<img src="../images/ex1/1-05.png" width="800" />

### Task 2 - Azure Functions の作成

- ホスティングオプション：Functions Premium
- リソースグループ名： functions-hands-on（既存のリソースグループを選択）
- 関数アプリ名： functions-hands-on-app（一意の名前を作成）
- コードまたはコンテナーイメージをデプロイしますか？： コード
- ランタイムスタック： Java
- ランタイムバージョン： Java 17
- リージョン： West US
- オペレーティングシステム： Linux
- Linux プラン：新規
- 価格プラン： エラスティック Plemium EP1 (ACU 合計 210, 3.5GB メモリ, 1vCPU)

<img src="../images/ex1/2-01.png" width="800" />
<img src="../images/ex1/2-02.png" width="800" />
<img src="../images/ex1/2-03.png" width="800" />
<img src="../images/ex1/2-04.png" width="800" />
<img src="../images/ex1/2-05.png" width="800" />
<img src="../images/ex1/2-06.png" width="800" />
<img src="../images/ex1/2-07.png" width="800" />
<img src="../images/ex1/2-08.png" width="800" />
<img src="../images/ex1/2-09.png" width="800" />
<img src="../images/ex1/2-10.png" width="800" />
<img src="../images/ex1/2-11.png" width="800" />
<img src="../images/ex1/2-13.png" width="800" />

### Task 3 - Azure Functions の確認

<img src="../images/ex1/3-01.png" width="800" />
<img src="../images/ex1/3-02.png" width="800" />

## まとめ

この演習では、Azure Functions アプリケーションを作成する方法を学びました。この演習では、Java で作成された Azure Functions アプリケーションを使用しました。

## 次のステップ

[Exercise 2 - Functionsアプリケーションのデプロイ（Java編）](./Exercise%202.md)

## 参考資料
- [Azure Functions の概要](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-overview?pivots=programming-language-java) 
- [Azure Functions のスケールとホスティング](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-scale) 
- [Azure Functions のベスト プラクティス](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-best-practices?tabs=csharp)
- [Azure Functions の Premium プラン](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-premium-plan?tabs=portal)
- [Azure Functions の専用ホスティング](https://learn.microsoft.com/ja-jp/azure/azure-functions/dedicated-plan) 
- [Azure Functions の Flex 従量課金プラン ホスティング ](https://learn.microsoft.com/ja-jp/azure/azure-functions/flex-consumption-plan) 
- [Azure Functions の Azure Container Apps ホスティング](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-container-apps-hosting) 
- [Azure Functions のセキュリティ保護](https://learn.microsoft.com/ja-jp/azure/azure-functions/security-concepts) 
- [Azure Functions での従量課金ベースのコストの見積もり](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-consumption-costs?tabs=flex-consumtion-plan%2Cportal) 


