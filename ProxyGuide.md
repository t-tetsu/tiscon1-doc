## プロキシの設定

自身のPCにプロキシが設定されている場合、別途設定が必要となります。  
※インターン当日はプロキシ設定が無い状態で行います。  

###自身の設定を確認する  
1. Internet Explorerを起動します。  
1. ツール > インターネットオプションを選択します。  
![自身のプロキシ設定確認1](image/proxy_setteing1.png)  
  
1. インターネットオプションウィンドより、接続 > LANの設定を選択します。  
![自身のプロキシ設定確認2](image/proxy_setteing2.png)

1. プロキシ サーバー内の「LANにプロキシサーバを使用する」にチェックがついていた場合、以降のプロキシの設定が必要となります。  
   記載されているアドレスとポートを控えておいてください。  
![自身のプロキシ設定確認3](image/proxy_setteing3.png)  
---
###IntelliJでのプロキシ設定  
1. IntelliJの上部メニューバーより、File > Settings を選択します。  
![IntelliJのプロキシ設定1](image/proxy_setteing_IntelliJ1.png)  
  
1. Settingsウィンドウが表示されるので、左のバーからAppearance & Behavior > 一般 > HTTP Proxyを選択します。  

1. 「HTTPプロキシを使用する」を選択し、各自の設定を記載します。  

1. 下部OKボタンを押下します。  
![IntelliJのプロキシ設定2](image/proxy_setteing_IntelliJ2.png)  
---
###Heroku動作のためのプロキシ設定  
環境変数に自身のプロキシについて設定する必要があります。  
1. スタート > コンピューターを右クリック > プロパティ > システムの詳細設定を選択してください。  
![Herokuのプロキシ設定1](image/proxy_setteing_Heroku1.png)  

1. システムのプロパティウィンドウの詳細設定 > 環境変数を選択します。  
![Herokuのプロキシ設定2](image/proxy_setteing_Heroku2.png)  

1. ユーザー環境変数内の新規ボタンを押下してください  
![Herokuのプロキシ設定3](image/proxy_setteing_Heroku3.png)  

1. 変数名に`HTTP_PROXY`、変数値に各自の設定を入力し、OKを選択します。  
![Herokuのプロキシ設定4](image/proxy_setteing_Heroku4.png)  

1. 同様に変数名に`HTTPS_PROXY`、変数値に各自の設定を入力し、OKを選択します。  
![Herokuのプロキシ設定5](image/proxy_setteing_Heroku5.png)  

1. 環境変数ウィンドウ内のOKボタンを押下してください。  
![Herokuのプロキシ設定6](image/proxy_setteing_Heroku6.png)  

1. スタート > すべてのプログラム > アクセサリ > コマンドプロンプトを選択してください。  

1. コマンドに`set`を入力し、先程入力した設定が反映されていることを確認してください。  
![Herokuのプロキシ設定7](image/proxy_setteing_Heroku7.png)  

---
###Webアプリケーション動作のための設定  
  
1. IntelliJを起動し、Project Viewより tiscon1 > respository > impl内のCachedGenreRepositoryをひらきます。
1. findFromApiメソッドを以下の様に編集します。
 
 編集前
 
         // プロキシ設定が不要の場合
         RestTemplate rest = new RestTemplate();
         // プロキシ設定が必要の場合
         // RestTemplate rest = myRest("proxy.co.jp", 8080);
 
 編集後
 
         // プロキシ設定が不要の場合
         // RestTemplate rest = new RestTemplate();
         // プロキシ設定が必要の場合
         RestTemplate rest = myRest("proxy.co.jp", 8080);　// 自身のプロキシアドレス、ポート番号を記載する
 
   同様に、Project Viewより tiscon1 > respository > impl内のCategoryRepositoryImpl内を編集します。  
 CategoryRepositoryImpl内は上記記載が2か所存在します。両方同様の編集を行って下さい。  
