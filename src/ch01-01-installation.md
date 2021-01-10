<!--
## Installation
-->
## インストール

<!--
The first step is to install Rust. We’ll download Rust through `rustup`, a
command line tool for managing Rust versions and associated tools. You’ll need
an internet connection for the download.
-->
Rustをインストールするための最初のステップは、Rust自体のバージョンや関連するツールを
管理するためのコマンドラインツールである`rustup`を通して、Rustをダウンロードすることです。
ダウンロードにはインターネット接続が必要です。

<!--
> Note: If you prefer not to use `rustup` for some reason, please see [the Rust
> installation page](https://www.rust-lang.org/tools/install) for other options.
-->
> 注：何かしらの理由で`rustup`を使いたくない場合は、[the Rust installation page
> ](https://www.rust-lang.org/tools/install) （英語）を読んで他の方法を確認してください。

<!--
The following steps install the latest stable version of the Rust compiler.
Rust’s stability guarantees ensure that all the examples in the book that
compile will continue to compile with newer Rust versions. The output might
differ slightly between versions, because Rust often improves error messages
and warnings. In other words, any newer, stable version of Rust you install
using these steps should work as expected with the content of this book.
-->
それから、最新の安定版Rustコンパイラーをインストールします。Rustの安定性の保証のおかげで、新しい
バージョンのコンパイラーであっても、本書でコンパイルできる例として掲載しているものはすべて、
継続してコンパイルが可能です。コンパイラーの出力は、僅かではありますが異なることがあります。これは
、Rustがエラーメッセージや警告の文章をしばしば改善するためです。言い換えれば、1.48以降の安定版
バージョンのRustであれば、どれをインストールしても本書の想定通りに進められるということです。

<!--
> ### Command Line Notation
>
> In this chapter and throughout the book, we’ll show some commands used in the
> terminal. Lines that you should enter in a terminal all start with `$`. You
> don’t need to type in the `$` character; it indicates the start of each
> command. Lines that don’t start with `$` typically show the output of the
> previous command. Additionally, PowerShell-specific examples will use `>`
> rather than `$`.
-->
> ### コマンドラインの表記法
> 
> この章、そして本書全体を通して、ターミナルで実行するコマンドを例示することがあります。ターミナル
> で実行するべき行はすべて`$`から始まっていますが、`$`を入力する必要はありません。`$`はコマンド
> の始まりを示すための文字です。また、`$`から始まっていない行は、基本的に直前に実行したコマンドの
> 出力です。一方PowerShell用の例では、`$`の代わりに`>`が用いられます。

<!--
### Installing `rustup` on Linux or macOS
-->
### LinuxまたはmacOSへの`rustup`のインストール

<!--
If you’re using Linux or macOS, open a terminal and enter the following command:
-->
LinuxかmacOSを使用している場合は、ターミナルを開いてこのコマンドを実行してください。

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

<!--
The command downloads a script and starts the installation of the `rustup`
tool, which installs the latest stable version of Rust. You might be prompted
for your password. If the install is successful, the following line will appear:
-->
このコマンドは、最新の安定版Rustをインストールするための`rustup`ツールをインストールしてくれる
シェルスクリプトをダウンロードして、実行します。

```text
Rust is installed now. Great!
```

<!--
Additionally, you’ll need a linker of some kind. It’s likely one is already
installed, but when you try to compile a Rust program and get errors indicating
that a linker could not execute, that means a linker isn’t installed on your
system and you’ll need to install one manually. C compilers usually come with
the correct linker. Check your platform’s documentation for how to install a C
compiler. Also, some common Rust packages depend on C code and will need a C
compiler. Therefore, it might be worth installing one now.
-->
加えて、なにかしらのリンカーが必要です。多くの場合既にインストールされていると思いますが、Rustで
書いたプログラムを実際にコンパイルしてみようとして、リンカーを実行できないというエラーが表示される
場合は、その環境にリンカーがインストールされていないということなので、手動でインストールする必要が
あります。通常、C言語のコンパイラーには適切なリンカーがついてきます。さらに、Rustのパッケージには
C言語のコードに依存しているものもあります。 今のうちからC言語のコンパイラーをインストールする価値
はあるでしょう。

<!--
### Installing `rustup` on Windows
-->
### Windowsへの`rustup`のインストール

<!--
On Windows, go to [https://www.rust-lang.org/tools/install][install] and follow
the instructions for installing Rust. At some point in the installation, you’ll
receive a message explaining that you’ll also need the C++ build tools for
Visual Studio 2013 or later. The easiest way to acquire the build tools is to
install [Build Tools for Visual Studio 2019][visualstudio]. When asked which
workloads to install make sure "C++ build tools" is selected and that the Windows 10 SDK and the English language pack components are included.
-->
Windowsへのインストールは、[https://www.rust-lang.org/ja/tools/install][install]の
指示にしたがって行ってください。インストールに際して、Visual Studio 2013以降用の
C++ビルドツールが必要だというメッセージが表示されるでしょう。最も簡単に入手する方法は、[Build
Tools for Visual Studio 2019][visualstudio]をインストールすることです。どれを
インストールするか尋ねられたら、"C++ build tools"が選択されていて、Windows 10 SDKと英語の
言語パックが含まれていることを確認してください。

<!--
[install]: https://www.rust-lang.org/tools/install
-->
[install]: https://www.rust-lang.org/ja/tools/install
[visualstudio]: https://visualstudio.microsoft.com/visual-cpp-build-tools/

<!--
The rest of this book uses commands that work in both *cmd.exe* and PowerShell.
If there are specific differences, we’ll explain which to use.
-->
以降のコマンドは、*cmd.exe*とPowerShellのどちらでも実行可能です。明確な違いがあるところでは、
*cmd.exe*とPowerShellのどちらを使うべきか説明します。

<!--
### Updating and Uninstalling
-->
### 更新とアンインストール

<!--
After you’ve installed Rust via `rustup`, updating to the latest version is
easy. From your shell, run the following update script:
-->
`rustup`を通じてRustをインストールした場合、最新のバージョンへの更新は簡単に行なえます。シェル
からこのスクリプトを実行してください

```console
$ rustup update
```

<!--
To uninstall Rust and `rustup`, run the following uninstall script from your
shell:
-->
Rustと`rustup`をアンインストールするためには、このスクリプトをシェルから実行してください。

```console
$ rustup self uninstall
```

<!--
### Troubleshooting
-->
### トラブルシューティング

<!--
To check whether you have Rust installed correctly, open a shell and enter this
line:
-->
正しくRustがインストールされているかを確かめるために、シェルを開いてこの通りに入力してください。

```console
$ rustc --version
```

<!--
You should see the version number, commit hash, and commit date for the latest
stable version that has been released in the following format:
-->
バージョン番号とそのリリースのコミットのハッシュと日付が、以下の形式で出力されるはずです。

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

<!--
If you see this information, you have installed Rust successfully! If you don’t
see this information and you’re on Windows, check that Rust is in your `%PATH%`
system variable. If that’s all correct and Rust still isn’t working, there are
a number of places you can get help. The easiest is the #beginners channel on
[the official Rust Discord][discord]. There, you can chat with other Rustaceans
(a silly nickname we call ourselves) who can help you out. Other great
resources include [the Users forum][users] and [Stack Overflow][stackoverflow].
-->
この通りに出力されていれば、Rustのインストールは正常に完了したということになります。Windowsを
使っていてこの通りに出力されていない場合は、Rustが`%PATH%`環境変数に含まれていることを確認
してください。問題ないのにそれでもRustが動かないときは、助けを得られる場所がいくつもあります。
最も簡単なのは、[Rust公式Discord][discord]の#beginnersチャンネルです。ここでは、あなたを
助けてくれるRustacean（Rustユーザーが自分たちを指して呼ぶときのニックネーム）たちとチャット
できます。その他の素晴らしい情報源として、[ユーザーフォーラム][users]と[Stack Overflow
][stackoverflow]があります。

[discord]: https://discord.gg/rust-lang
[users]: https://users.rust-lang.org/
[stackoverflow]: https://stackoverflow.com/questions/tagged/rust

<!--
### Local Documentation
-->
### ローカルドキュメンテーション

<!--
The installation of Rust also includes a copy of the documentation locally, so
you can read it offline. Run `rustup doc` to open the local documentation in
your browser.
-->
Rustのインストールの際には、ドキュメントのローカルのコピーもついてくるので、オフラインで読むこと
ができます。ローカルのドキュメントを開くには、`rustup doc`を実行してください。

<!--
Any time a type or function is provided by the standard library and you’re not
sure what it does or how to use it, use the application programming interface
(API) documentation to find out!
-->
標準ライブラリーから提供されている型や関数が、何をするものでどのように使えばよいのかわからないとき
は、アプリケーション・プログラミング・インターフェース（API）ドキュメントを使って調べてみましょう
！