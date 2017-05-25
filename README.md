## python

* インフラ構成管理ツール
  * OSの起動を自動化するツール
    * Vagrant
      * OSがインストールされた専用のディスクイメージ「Box」を使用して仮想マシンを作成
      * Vagrantfileという設定ファイルをRubyで作成して仮想マシンを設定
    * Docker
      * ホストOS上に論理的な区画（コンテナ）を作るコンテナ型仮想化を採用
      * 業務アプリの実行モジュール・ライブラリ群・インフラ設定をコンテナにまとめて管理するため、Dockerをインストールしたあらゆる環境で動作できる
      * オーバーヘッドが少ないため、軽量で高速に動作する
      * Dockerfileという設定ファイルに基づいて設定
      * コンテナ型仮想化に対して、VirtualBoxといった仮想化ソフト上に仮想環境を構築するホスト型仮想化や、ハードウエア上に仮想化を専門に行うミドルウエアである「ハイパーバイザー」を配置するハイパーバイザー型仮想化がある
  * OSやミドルウエアの設定を自動化するツール
    * Chef
      * 「Chef Server」と「Chef Client」を導入して、クライアントサーバ型のアーキテクチャで複数台のサーバを自動構成することができる
      * また「Chef Solo」コマンドを用いてスタンドアロンで利用することもできる
      * 「Chef Client」はクラウドの仮想環境でも扱うことができる
      * Rubyの文法をベースにした「Recipe」というプログラムに基づいて設定される
      * 「Knife」コマンドで管理する
    * Ansible
      * Pythonで実装されている
    * Puppet

* ファイル形式
  * YAML
    * スペースによるインデントを使ってデータの階層構造を示す
    * XMLやJSONと違って、ファイルの中身のほとんどがデータのため、手作業でのメンテナンスが必要な各種データファイルに適している
```
JFrame:
    defaultCloseOperation: JFrame.EXIT_ON_CLOSE
    title: Test Frame
    width: 800
    height: 400
    components:
        - JTextArea:
             name: textArea1
             text: |
               This is a really long text
               that spans multiple lines (but preserves new lines).
               It does not need to be escaped with special brackets,
               CDATA tags, or anything like that
        - JButton:
             name: button2
             text: Button 2
```

  * JSON
    * 中かっこ（{}）と角かっこ（[]）によってデータの階層構造を示す
    * 効率性の向上やファイルサイズの節約に適している　
```
[
  {"path": "C:\\Download\\paper",
   "extension": ["pdf", "doc"],
   "destination": ["C:\\Dropbox\\論文\\*", "C:\\My Documents\\査読\\*"]},
  {"path": "C:\\Download\\music",
   "extension": ["mp3", "wav", "mp4"],
   "destination": ["C:\\Dropbox\\音楽\\*", "C:\\My Music\\*"]}
]
```
  * XML
    * タグのネストによってデータの階層構造を示す
```
<?xml version="1.0"?>
<catalog>
   <book id="bk112">
      <author>Galos, Mike</author>
      <title>Visual Studio 7: A Comprehensive Guide</title>
      <genre>Computer</genre>
      <price>49.95</price>
      <publish_date>2001-04-16</publish_date>
      <description>Microsoft Visual Studio 7 is explored in depth,
      looking at how Visual Basic, Visual C++, C#, and ASP+ are 
      integrated into a comprehensive development 
      environment.</description>
   </book>
</catalog>
```
