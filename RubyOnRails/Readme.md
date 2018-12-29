#Ruby 2.5.3 + Devkit Windows Installerでインストール → RubyMineで作成したRoRプロジェクトでSqlite3のエラーが発生

__Big thanks to：https://qiita.com/yoru722/items/8a633d71148de0f0ae1f__

プログラム設定で毎回大混乱しますが、今回のチャレンジはRuby on Rails. Ruby公式ホームページからRuby＋Devkitのインストールーー＞Ruby on Railsのインストールして、RubyMineでお試しプロジェクトを作成しました。次に `start application` (= `rails server`と同様 )を押したら・・・

> cannot load such file -- sqlite3/sqlite3_native (LoadError)

というエラーが発生。

グーグル神に相談してみたら、上のqiitaポストを発見。
どうもありがとうございます。m(_ _)m

現在（2018.12)時点では最新バージョンが変わりましたので、

```
gem uninstall -a sqlite3 
```

を実施。その後

```
gem install sqlite3 -v "=1.3.13" --platform=ruby -- --with-sqlite3-include=C:\temp\sqlite-amalgamation-3260000 --with-sqlite3-lib=C:\Ruby25-x64\bin
```
と実施します。End codeが 0で終わればOK。

>★　何か月、何年後にこのreadmeを読む人のために↓
>- "=1.3.13" ---> 自分のsqlite3のversionに変更
>
>- "=sqlite-amalgamation-3260000" ---> 自分のsqlite3(Source Code) versionに変更
>
>- "C:\temp\"、"C:\Ruby25-x64\bin" ---> 各ファイルが入っているフォルダに変更


しかし、また`start application`を押しても動かず・・・
原因は dependency fileのlocationを保存するキャッシュファイルと
RubyMineがインストールしてくれたsqlite3のgemspecファイルでした。

__解決方法__

１．｛RoRプロジェクトルートfolder}/tmp/cache/bootsnap-load-path-cacheファイルを削除
 (再生成されるのでご心配なく)

２．｛Rubyインストールfolder}/lib/ruby/gems/{ruby version}]/specifications/sqlite3-1.3.13-x64-mingw32.gemspecを削除。

これで解決。
`start application`を押したら、Yay! You’re on Rails!に無事到着でした。