### 20180119
* Unity2017でもUnity5でも成功  
* プロジェクトディレクトリも、深くなっても成功
* unityのコマンドラインビルドは、

```
https://qiita.com/sango/items/474efb4c016a136c84ce
```
を参考にbuild.csを作成して、以下のコマンドを入力

> "C:\Program Files\Unity\Editor\Unity.exe" -batchmode -quit -projectPath <projectfolder> -executeMethod BuildClass.Build

※-logFileコマンドはなぜか失敗する。

* 視覚的に確認したい場合、-batchmodeを入れなければ、Unityが立ち上がるので処理を視認できる。

* Jenkins上でのバッチ
プロジェクトフォルダの場所は、バッチ上に記述するか、下のurlのようにワークディレクトリをカスタムする。
https://qiita.com/yohekan/items/9f556a0054e4071ddef0#_reference-c04cb0ba55b795d337e9

### 20180123
* ミスを発見
  * Build.csには、出力先のパスが記載されている。個々を修正していなかったため、期待していたパスに出力されていなかった模様。
* gitに紐付けたローカルレポジトリ内で、Jenkinsビルドできた。