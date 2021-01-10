## Hello, World!

<!--
Now that you’ve installed Rust, let’s write your first Rust program. It’s
traditional when learning a new language to write a little program that prints
the text `Hello, world!` to the screen, so we’ll do the same here!
-->
Rustをインストールし終わったので、はじめてのRustのプログラムを書いてみましょう。新しい言語を
習得するときは伝統的に、`Hello, world!`という文字を出力するだけの小さなプログラムを書きます。

<!--
> Note: This book assumes basic familiarity with the command line. Rust makes
> no specific demands about your editing or tooling or where your code lives, so
> if you prefer to use an integrated development environment (IDE) instead of
> the command line, feel free to use your favorite IDE. Many IDEs now have some
> degree of Rust support; check the IDE’s documentation for details. Recently,
> the Rust team has been focusing on enabling great IDE support, and progress
> has been made rapidly on that front!
-->
> 注意：本書は、コマンドラインの基本的な知識を前提としています。コードの保存場所や編集方法、
> 使用するツールについて、特別何かを要求することはありません。そのため、コマンドラインの代わりに
> 統合開発環境（IDE）使用したい場合は、好きなものを使ってください。多くのIDEは、Rustのサポート
> をある程度してくれます。詳細はIDEのドキュメントを確認してください。最近、Rustチームは。IDEが
> 優れたサポートを提供できるようにすることに焦点を置いており、その点では急速に進歩してきています。

<!--
### Creating a Project Directory
-->
### プロジェクトディレクトリの作成

<!--
You’ll start by making a directory to store your Rust code. It doesn’t matter
to Rust where your code lives, but for the exercises and projects in this book,
we suggest making a *projects* directory in your home directory and keeping all
your projects there.
-->
はじめにRustのコードを保管するディレクトリをつくりましょう。どこにコードを置くかは、Rustにとって
問題ではありませんが、本書での演習やプロジェクトで書くコードをまとめて置いておくために、
*projects*ディレクトリをあなたのホームディレクトリに作成することをおすすめします。

<!--
Open a terminal and enter the following commands to make a *projects* directory
and a directory for the “Hello, world!” project within the *projects* directory.
-->
*projects*ディレクトリと、その中に”Hello, world!”プロジェクト用のディレクトリを作成するため
に、ターミナルを開いて次のコマンドを実行してください。

<!--
For Linux, macOS, and PowerShell on Windows, enter this:
-->
Linux、macOSまたはWindowsのPowerShellでは、以下の通りに入力してください。 

```console
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

<!--
For Windows CMD, enter this:
-->
Windows CMDを用いる場合は、こちらです。

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

<!--
### Writing and Running a Rust Program
-->
### Rustのプログラムを書いて実行する

<!--
Next, make a new source file and call it *main.rs*. Rust files always end with
the *.rs* extension. If you’re using more than one word in your filename, use
an underscore to separate them. For example, use *hello_world.rs* rather than
*helloworld.rs*.
-->
つぎに、*main.rs*という名前でソースファイルを作成しましょう。Rustのファイルの名前は、常に
*.rs*拡張子で終わります。ファイルの名前に２つ以上の単語を使いたいときは、単語の区切りに
アンダースコアを挟んでください。例えば、*helloworld.rs*とするよりも*hello_world.rs*とした
ほうが良いでしょう。

<!--
Now open the *main.rs* file you just created and enter the code in Listing 1-1.
-->
さて、たった今作成した*main.rs*ファイルを開いて、リスト１－１の通りにコードを入力しましょう。

<!--
<span class="filename">Filename: main.rs</span>
-->
<span class="filename">ファイル名：main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

<!--
<span class="caption">Listing 1-1: A program that prints `Hello, world!`</span>
-->
<span class="caption">リスト１－１：`Hello, world!`を出力するプログラム</span>

<!--
Save the file and go back to your terminal window. On Linux or macOS, enter
the following commands to compile and run the file:
-->
ファイルを保存して、ターミナルのウィンドウに戻ってください。LinuxとmacOSでは、このコマンドを
入力して、このファイルをコンパイル、実行してください。

```console
$ rustc main.rs
$ ./main
Hello, world!
```

<!--
On Windows, enter the command `.\main.exe` instead of `./main`:
-->
Windowsでは、`./main`の代わりに、`.\main.exe`と入力してください。

```powershell
> rustc main.rs
> .\main.exe
Hello, world!
```

<!--
Regardless of your operating system, the string `Hello, world!` should print to
the terminal. If you don’t see this output, refer back to the
[“Troubleshooting”][troubleshooting] part of the Installation
section for ways to get help.
-->
OSに関わらず、文字列`Hello, world!`が、ターミナルに出力されました。この通りに出力されない場合
は、インストールの節の[「トラブルシューティング」][troubleshooting]に戻って、助けを得る方法を
参照してください。

<!--
If `Hello, world!` did print, congratulations! You’ve officially written a Rust
program. That makes you a Rust programmer—welcome!
-->
`Hello, world!`が出力された方、おめでとうございます。あなたは正式にRustのプログラムを書いたの
です。晴れてあなたは、Rustプログラマーの一員です。

<!--
### Anatomy of a Rust Program
-->
### Rustプログラムの解剖学

<!--
Let’s review in detail what just happened in your “Hello, world!” program.
Here’s the first piece of the puzzle:
-->
”Hello, world!”のプログラム内で何が起こったのか、詳細を見ていきましょう。今ここに、パズルの
一つ目のピースがあります。

```rust
fn main() {

}
```

<!--
These lines define a function in Rust. The `main` function is special: it is
always the first code that runs in every executable Rust program. The first
line declares a function named `main` that has no parameters and returns
nothing. If there were parameters, they would go inside the parentheses, `()`.
-->
これらの行は、Rustでの関数の定義をしています。`main`関数は特別で、これは、実行可能なRustの
プログラム内で最初に走るコードです。

<!--
Also, note that the function body is wrapped in curly brackets, `{}`. Rust
requires these around all function bodies. It’s good style to place the opening
curly bracket on the same line as the function declaration, adding one space in
between.
-->
また、関数の本体が波括弧`{}`で囲まれていることに注意してください。Rustでは、常に関数の中身を
波括弧で囲む必要があります。関数の宣言と同じ行に、間に空白を一つ挟んで開き波括弧を置くのは、良い
書き方です。

<!--
If you want to stick to a standard style across Rust projects, you can use an 
automatic formatter tool called `rustfmt` to format your code in a particular
style. The Rust team has included this tool with the standard Rust distribution,
like `rustc`, so it should already be installed on your computer! Check the online
documentation for more details.
-->
プロジェクト全体でコードスタイルの基準に忠実にありたい場合、`rustfmt`と呼ばれる自動整形ツールを
使用することで、特定のスタイルで整形することができます。Rustチームは、このツールを`rustc`の
ような標準的なRustディストリビューションに含めています。そのため、あなたのコンピュータには既に
インストールされているはずです。詳細については、オンラインドキュメントを参照してください。

<!--
Inside the `main` function is the following code:
-->
`main`関数の中は、次の通りです。

```rust
    println!("Hello, world!");
```

<!--
This line does all the work in this little program: it prints text to the
screen. There are four important details to notice here.
-->
この行が、この小さなプログラムの仕事のすべてをしています。これが、画面に文字を出力します。ここには
注目するべき４つの重要な要素があります。

<!--
First, Rust style is to indent with four spaces, not a tab.
-->
１つ目に、Rustの書き方では、インデントはタブではなく４つのスペースで表します。

<!--
Second, `println!` calls a Rust macro. If it called a function instead, it
would be entered as `println` (without the `!`). We’ll discuss Rust macros in
more detail in Chapter 19. For now, you just need to know that using a `!`
means that you’re calling a macro instead of a normal function.
-->
２つ目に、`println!`は、Rustのマクロを呼び出します。もしこれが関数なら、`println`（`!`無し）
と表記されます。Rustのマクロは、第１９章でより詳細に扱います。一先ずは、関数の代わりにマクロを
呼び出すためには`!`をつける必要が有るということだけ知っておいてください。

<!--
Third, you see the `"Hello, world!"` string. We pass this string as an argument
to `println!`, and the string is printed to the screen.
-->
３つ目に、文字列`"Hello, world!"`がコード中にあります。この文字列を`println!`に引数として
渡しており、これがスクリーンに出力されます。

<!--
Fourth, we end the line with a semicolon (`;`), which indicates that this
expression is over and the next one is ready to begin. Most lines of Rust code
end with a semicolon.
-->
４つ目に、この行はセミコロン（`;`）で終わっています。セミコロンはこの式が終わり次の式が始まること
を表しています。Rustのコードの行は、ほとんどがセミコロンで終わります。

<!--
### Compiling and Running Are Separate Steps
-->
### コンパイルと実行は別のステップ

<!--
You’ve just run a newly created program, so let’s examine each step in the
process.
-->
たった今作ったプログラムを実行してみたので、それぞれのステップを検証してみましょう。

<!--
Before running a Rust program, you must compile it using the Rust compiler by
entering the `rustc` command and passing it the name of your source file, like
this:
-->
Rustのプログラムは、実行する前にRustコンパイラーを使ってコンパイルする必要があります。この例の
ように`rustc`のコマンドにソースファイルの名前を渡しましょう。

```console
$ rustc main.rs
```

<!--
If you have a C or C++ background, you’ll notice that this is similar to `gcc`
or `clang`. After compiling successfully, Rust outputs a binary executable.
-->
CやC++の経験がある人は、これが`gcc`や`clang`に似ていることに気づくかもしれません。コンパイルに
成功したら、Rustは実行可能なバイナリを出力します。

<!--
On Linux, macOS, and PowerShell on Windows, you can see the executable by
entering the `ls` command in your shell. On Linux and macOS, you’ll see two
files. With PowerShell on Windows, you’ll see the same three files that you
would see using CMD.
-->
Linux、macOS、またはWindowsのPowerShellでは、`ls`コマンドを使うことで実行ファイルを確認
することができます。LinuxとmacOSでは、２つのファイル名が表示されます。Windowsの場合、
PowerShellでは、CMDを使った例と同様に３つのファイルが表示されます。

```text
$ ls
main  main.rs
```

<!--
With CMD on Windows, you would enter the following:
-->
WindowsのCMDでは、このように入力します。

```cmd
> dir /B %= /B はファイル名だけを表示するためのオプション =%
main.exe
main.pdb
main.rs
```

<!--
This shows the source code file with the *.rs* extension, the executable file
(*main.exe* on Windows, but *main* on all other platforms), and, when using
Windows, a file containing debugging information with the *.pdb* extension.
From here, you run the *main* or *main.exe* file, like this:
-->
*.rs*の拡張子で始まるソースコードファイル、実行ファイル（Windowsでは*main.exe*、他の
すべての環境では*main*）、それからWindowsを使っている場合はデバッグ情報が記述されている、
拡張子が<!-- -->*.pdb*のファイルが表示されます。*main*または*main.exe*は、このように
実行します。

```console
$ ./main # Windowsの場合は .\main.exe
```

<!--
If *main.rs* was your “Hello, world!” program, this line would print `Hello,
world!` to your terminal.
-->
もし*main.rs*が”Hello, world!”のプログラムならば、これを実行すると`Hello, world`が
ターミナルに表示されるでしょう。

<!--
If you’re more familiar with a dynamic language, such as Ruby, Python, or
JavaScript, you might not be used to compiling and running a program as
separate steps. Rust is an *ahead-of-time compiled* language, meaning you can
compile a program and give the executable to someone else, and they can run it
even without having Rust installed. If you give someone a *.rb*, *.py*, or
*.js* file, they need to have a Ruby, Python, or JavaScript implementation
installed (respectively). But in those languages, you only need one command to
compile and run your program. Everything is a trade-off in language design.
-->
RubyやPython、JavaScriptのような動的言語に親しんできた人は、コンパイルと実行を別のステップに
分けて行うことに慣れていないかもしれません。Rustは事前コンパイル言語です。これは、プログラムを
コンパイルしたあと、実行ファイルを他の誰かにあげることができ、またそれを受け取った人は、Rust
をインストールしなくても実行できます。*.rb* や *.py*、*.js*を渡す場合、受け取った人は各々が
それぞれRubyやPython、JavaScriptの実装をインストールする必要があります。

<!--
Just compiling with `rustc` is fine for simple programs, but as your project
grows, you’ll want to manage all the options and make it easy to share your
code. Next, we’ll introduce you to the Cargo tool, which will help you write
real-world Rust programs.
-->
単純なプログラムであれば`rustc`でコンパイルするだけでも十分ですが、プロジェクトが成長してくると、
すべてのオプションの管理と簡単なコードの共有をしたくなってきます。次の節では、現実にRustで
プログラムを書くことを助けてくれる、Cargoというツールを紹介します。

[troubleshooting]: ch01-01-installation.html#トラブルシューティング
