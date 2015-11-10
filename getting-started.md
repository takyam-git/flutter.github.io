---
layout: page
title: Getting Started with Flutter
nav_title: Getting Started
permalink: /getting-started/
---

Flutterは現在MacとLinuxでの開発をサポートしています。
Windowsのサポートは現在作業中です。

まずはDart SDKが必要です。
FlutterはDart SDKのバージョン1.12.2以上が必要です。

[Dart SDK](https://www.dartlang.org/downloads/)のインストール:

- Mac: `brew tap dart-lang/dart && brew install dart` を使うか、homebrewを使わないのであれば [latest stable channel build](https://www.dartlang.org/downloads/archive/) から入手してください。
- Linux: [www.dartlang.org/downloads/linux.html](https://www.dartlang.org/downloads/linux.html) を参照してください。
- Windows: しばらくお待ち下さい。Windowsサポートは現在作業中です。

`pub` コマンドが実行可能な `PATH` になってるか確認してください。

Dart SDKのインストールに成功したら、`flutter` コマンドラインツールをパスに追加して有効化します：

```
$ pub global activate flutter
$ export PATH=$HOME/.pub-cache/bin:$PATH
```

`my_app` という名前のプロジェクトを `flutter` コマンドで作ってみましょう：

```
$ flutter init -o my_app
```

このコマンドは[マテリアルデザイン](https://www.google.com/design/spec/material-design/introduction.html)を使った
簡単なデモアプリを `my_app` ディレクトリに作成します。

デモアプリのコードが `my_app/lib/main.dart` にあります。
`runApp` を使って `MaterialApp` ウィジェットを実行する `main` ファンクションから処理が開始されます。
`MaterialApp` ウィジェットはアプリの各画面毎に1つのエントリをもつルートマップによって構成されています。
今回の場合 `/` と名前がつけられた `FlutterDemo` コンポーネントをビルドする1つのホーム画面だけが設定されています。

Flutterでアプリケーションのビルドについてもっと知りたい場合は [tutorial](/tutorial/) をご覧ください。

Androidデバイスのセットアップ
------------------------------

現在のFlutterはKitkat（かそれ以降の）バージョンのAndroidOSが動いているAndroidデバイスが必要です。

 - `adb` ツールを [Android SDK](https://developer.android.com/sdk/installing/index.html?pkg=tools) からインストールします:
  - Mac: `brew install android-platform-tools`
  - Linux: `sudo apt-get install android-tools-adb`
    - もしあなたが使っているLinuxディストリビューションが提供する `adb` のバージョンがすごく古い場合は、
      [Android SDK を手動でインストールする](https://developer.android.com/sdk/installing/index.html?pkg=tools) 必要があるかもしれません。
 
 - あなたのAndroiデバイスの `設定 > 端末情報` を開いて `ビルド番号` の欄を7回タップして開発者モードを有効にしてください 

 - `設定 > 開発者向けオプション` から `USBデバッグ` を有効化してください。
  - （訳注: 原文ではAndroid debuggingとなっておりこれがどの設定を指すのか分かりませんが、前後の文章からUSBデバッグの可能性が高いです)

- USBケーブルを使ってパソコンとAndroidデバイスを接続します。
  Androidデバイスにプロンプトが表示されたらパソコンがAndroidデバイスにアクセスできるように認証を行ってください。

Flutterアプリケーションの実行
-----------------------------

AndroidデバイスでFlutterアプリケーションを動かすのに `flutter` コマンドを使います。
まず、デモアプリのディテクトリ（ `pubspec.yaml がある階層です）に移動します。

そして `start` コマンドでアプリケーションを開始します。

```
$ flutter start
$ flutter logs
```

`logs` コマンドは、`print` 文やハンドルしてない例外などのアプリケーションからの出力を見ることができます。
古いメッセージに混乱しないように `flutter logs --clear` を使うことも可能です。

Getting Started with Atom
-------------------------

Flutterは [Atom](https://atom.io/) をIDEとして使えますし、
コマンドラインツールを使うことで任意のエディタでFlutterアプリケーションを開発することができます。
しかし我々はまだ最高の開発体験をお届けするためにAtomのFlutterプラグインを開発している最中です。

AtomとFlutterプラグインをインストールする手順は
[dart-atom.github.io/dartlang](http://dart-atom.github.io/dartlang/)を参照してください。

Debugging
---------

Flutterはデバッグとプロファイリングのために [Observatory](https://www.dartlang.org/tools/observatory/) を使っています。
アプリを起動しているあいだ、ブラウザで [http://localhost:8181/](http://localhost:8181/) から Observatory にアクセスできます。

スタンドアロンなAPKをビルドする
-------------------------

あなたのアプリケーションを含むスタンドアロンなAPKをビルドする事は可能ではありますが、今はまだ難しいです。
もしあなたが勇敢なら [examples/stocks](https://github.com/flutter/flutter/tree/master/examples/stocks) から
我々が `Stocks.apk` をどのようにビルドしたのか見ることができます。

最終的にはこれらの作業はもっと簡単に、そしてAndroid以外のプラットフォームもサポートする予定ですが、
今はまだ作業中です。
