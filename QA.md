## QA一覧

###mvnが正常に動作しない (mvn --versionコマンドが失敗する)

![IntelliJのプロキシ設定1](image/qa_javahome.png)  
![IntelliJのプロキシ設定1](image/qa_mvnpath.png)  

JDKまたはMavenの環境変数設定が誤っている可能性があります。
JDK,Mavenをインストールしたディレクトリと環境変数が一致しているかを確認してみてください。
(環境変数に指定しているディレクトリが実際に存在しているか確認してください)

#####JDKの環境変数設定
1.システム環境変数『Path』　
　　例)C:\Program Files\Java\jdk1.8.0_111\bin
2.システム環境変数『JAVA_HOME』
　　例)C:\Program Files\Java\jdk1.8.0_111
※ユーザー環境変数とシステム環境変数の両方に同じ変数名で値が設定されている場合、ユーザー環境変数の値が優先されてしまいます。ユーザー環境変数に『JAVA_HOME』が存在する場合、そちらは削除してください。  

【補足】環境変数『Path』だけはユーザー変数がシステム変数を上書きせず、両方の値が「;」で連結された設定となります。
#####Mavenの環境変数設定
1.システム環境変数『Path』
　　例)C:\Program Files\apache-maven-3.2.5\bin
※環境構築手順に記載しているように、ダウンロードしたMavenは「C:\Program Files」に格納してください。そうした場合、Pathの変数値は上記例の通りになります。
