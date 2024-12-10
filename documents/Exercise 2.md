# Functionsアプリケーションのデプロイ（Java編）

## 概要

この演習では、Azure Functions アプリケーションを作成し、Azure Functions アプリケーションをデプロイする方法を学びます。この演習では、Java で作成された Azure Functions アプリケーションを使用します。

## 作業手順

### Task 1 - コンテンツを Fork する

#### ステップ 1: GitHub にログインする
```
https://github.com/
```
<img src="../images/ex2/1-01.png" width="800" />
<img src="../images/ex2/1-02.png" width="800" />

#### ステップ 2: リポジトリを Fork する
```
https://github.com/h-morozumi/AzureFunctions-Hands-on
```
<img src="../images/ex2/1-04.png" width="800" />
<img src="../images/ex2/1-05.png" width="800" />
<img src="../images/ex2/1-06.png" width="800" />

### Task 2 - アプリケーションの修正

<img src="../images/ex2/2-01.png" width="800" />
<img src="../images/ex2/2-02.png" width="800" />
<img src="../images/ex2/2-08.png" width="800" />

``` xml
    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <java.version>17</java.version>
        <azure.functions.maven.plugin.version>1.36.0</azure.functions.maven.plugin.version>
        <azure.functions.java.library.version>2.2.0</azure.functions.java.library.version>
        <functionAppName>functions-hands-on-app</functionAppName>
    </properties>
```

``` xml
            <plugin>
                <groupId>com.microsoft.azure</groupId>
                <artifactId>azure-functions-maven-plugin</artifactId>
                <version>${azure.functions.maven.plugin.version}</version>
                <configuration>
                    <!-- function app name -->
                    <appName>${functionAppName}</appName>
                    <!-- function app resource group -->
                    <resourceGroup>functions-hands-on</resourceGroup>
                    <!-- function app service plan name -->
                    <appServicePlanName>ASP-handsondemo-1-SaaS</appServicePlanName>
                    <!-- function app region-->
                    <!-- refers https://github.com/microsoft/azure-maven-plugins/wiki/Azure-Functions:-Configuration-Details#supported-regions for all valid values -->
                    <region>westus</region>
                    <!-- function pricingTier, default to be consumption if not specified -->
                    <!-- refers https://github.com/microsoft/azure-maven-plugins/wiki/Azure-Functions:-Configuration-Details#supported-pricing-tiers for all valid values -->
                    <pricingTier>EP1</pricingTier>
                    <!-- Whether to disable application insights, default is false -->
                    <!-- refers https://github.com/microsoft/azure-maven-plugins/wiki/Azure-Functions:-Configuration-Details for all valid configurations for application insights-->
                    <!-- <disableAppInsights></disableAppInsights> -->
                    <appInsightsInstance>fnchelloworld</appInsightsInstance>
                    <runtime>
                        <!-- runtime os, could be windows, linux or docker-->
                        <os>Linux</os>
                        <javaVersion>17</javaVersion>
                    </runtime>
                    <appSettings>
                        <property>
                            <name>FUNCTIONS_EXTENSION_VERSION</name>
                            <value>~4</value>
                        </property>
                    </appSettings>
                </configuration>
                <executions>
                    <execution>
                        <id>package-functions</id>
                        <goals>
                            <goal>package</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
```

#### 関数名とリソースグループ名を取得する
<img src="../images/ex2/2-03.png" width="800" />

#### プラン名を取得する
<img src="../images/ex2/2-05.png" width="800" />

#### Application Insights のインスタンス名を取得する
<img src="../images/ex2/2-06.png" width="800" />

#### 全体の構成
<img src="../images/ex2/2-07.png" width="800" />

#### 保存する
<img src="../images/ex2/2-04.png" width="800" />
<img src="../images/ex2/2-09.png" width="800" />
<img src="../images/ex2/2-10.png" width="800" />


### Task 3 - Azure Functions アプリケーションのデプロイ

#### リポジトリ名をコピーする
<img src="../images/ex2/3-01.png" width="800" />

#### Cloud Shell を起動する
<img src="../images/ex2/3-03.png" width="800" />

#### Cloud Shell にて以下のコマンドを実行する

##### リポジトリをクローンする
``` bash
git clone https://github.com/ユーザー名/AzureFunctions-Hands-on.git
```

##### ディレクトリに移動する
``` bash
cd AzureFunctions-Hands-on/functions-java-demo
```

##### アプリケーションのビルド
``` bash
./mvnw clean package
```

##### アプリケーションのデプロイ
``` bash
./mvnw azure-functions:deploy -e
```

<img src="../images/ex2/3-05.png" width="800" />
<img src="../images/ex2/3-07.png" width="800" />
<img src="../images/ex2/3-08.png" width="800" />
<img src="../images/ex2/3-09.png" width="800" />
<img src="../images/ex2/3-10.png" width="800" />
<img src="../images/ex2/3-11.png" width="800" />
<img src="../images/ex2/3-12.png" width="800" />


### Task 4 - デプロイの確認

#### HttpTrigger の確認

<img src="../images/ex2/4-01.png" width="800" />
<img src="../images/ex2/4-02.png" width="800" />
<img src="../images/ex2/4-03.png" width="800" />
<img src="../images/ex2/4-04.png" width="800" />
<img src="../images/ex2/4-05.png" width="800" />
<img src="../images/ex2/4-06.png" width="800" />

#### TimerTrigger の確認

<img src="../images/ex2/5-01.png" width="800" />
<img src="../images/ex2/5-02.png" width="800" />


### Task 5 - Application Insights の確認

<img src="../images/ex2/6-01.png" width="800" />
<img src="../images/ex2/6-02.png" width="800" />
<img src="../images/ex2/6-03.png" width="800" />
<img src="../images/ex2/6-04.png" width="800" />

## まとめ

この演習では、Azure Functions アプリケーションを作成し、Azure Functions アプリケーションをデプロイする方法を学びました。この演習では、Java で作成された Azure Functions アプリケーションを使用しました。

## 参考資料

- [Azure Functions でサポートされている言語](https://learn.microsoft.com/ja-jp/azure/azure-functions/supported-languages?tabs=isolated-process%2Cv4&pivots=programming-language-java) 
- [Azure Functions のデプロイ テクノロジ](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-deployment-technologies?tabs=windows) 
- [Azure Functions のトリガーとバインド](https://learn.microsoft.com/ja-jp/azure/azure-functions/functions-triggers-bindings?tabs=isolated-process%2Cnode-v4%2Cpython-v2&pivots=programming-language-java) 
- [Azure Functions: Configuration Details · microsoft/azure-maven-plugins Wiki](https://github.com/microsoft/azure-maven-plugins/wiki/Azure-Functions:-Configuration-Details) 