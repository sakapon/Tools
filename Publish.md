## How to Publish App

KTools アプリケーションを ClickOnce で発行するための手順。

### Git の設定
改行コードが自動的に変換されないように、次のコマンドを実行する。

```
$ git config --global core.autocrlf false
```

設定を確認するためのコマンド:

```
$ git config --list
```

### 証明書の準備
証明書のファイル自体は別の場所で管理する。

* ルート証明書 (Root CA)
  * .cer を証明書ストアのルート (Root) にインストールする
* 発行者証明書 (KTools Publisher)
  * .pfx を証明書ストアの個人 (My) にインストールする (パスワードが必要)

### プロジェクトの設定

#### [署名]
* [ストアから選択] をクリックして、[KTools Publisher] を選択する

#### [発行]
* **発行フォルダーの場所** *..\\..\\..\\Tools\\2015\\PlanetClock\\*
* **リビジョンのインクリメント** False

#### [発行] - [更新]
自動更新を有効にする場合は設定する。

#### [発行] - [オプション]
* **発行者名** KTools
* **スイート名** KTools *2015*
* **製品名** *Planet Clock*

### 発行
* Tools リポジトリの分岐を gh-pages に切り替える
* ソリューション構成を [Release] に切り替える
* **バージョンの発行** AssemblyInfo に記述されたバージョン
* [今すぐ発行] をクリックする
  * MSBuild でもよい
