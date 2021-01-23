## Hello, World!

<!--
Now that you’ve installed Rust, let’s write your first Rust program. It’s
traditional when learning a new language to write a little program that prints
the text `Hello, world!` to the screen, so we’ll do the same here!
-->
Rustをインストールし終わったので、はじめてのRustのプログラムを書いてみましょう。
新しい言語を習得するときは伝統的に、`Hello, world!`という文字を出力するだけの
小さなプログラムを書きます。

<!--
> Note: This book assumes basic familiarity with the command line. Rust makes
> no specific demands about your editing or tooling or where your code lives, so
> if you prefer to use an integrated development environment (IDE) instead of
> the command line, feel free to use your favorite IDE. Many IDEs now have some
> degree of Rust support; check the IDE’s documentation for details. Recently,
> the Rust team has been focusing on enabling great IDE support, and progress
> has been made rapidly on that front!
-->
> 注意：本書は、コマンドラインの基本的な知識を前提としています。コードの保存場所
> や編集方法、使用するツールについて、特別何かを指定することはありません。
> そのため、コマンドラインの代わりに統合開発環境（IDE）使用したい場合は、好きな
> ものを使ってください。多くのIDEは、Rustのサポートをある程度してくれます。詳細
> はIDEのドキュメントを確認してください。最近Rustチームは、IDEが優れたサポートを
> 提供できるようにすることに焦点を置いており、その点では急速に進歩してきています
> 。

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
はじめにRustのコードを保管するディレクトリをつくりましょう。どこにコードを置くか
は、Rustにとって問題ではありませんが、本書での演習やプロジェクトで書くコードを
まとめて置いておくために、*projects*ディレクトリをあなたのホームディレクトリに
作成することをおすすめします。

<!--
Open a terminal and enter the following commands to make a *projects* directory
and a directory for the “Hello, world!” project within the *projects* directory.
-->
*projects*ディレクトリと、その中に”Hello, world!”プロジェクト用のディレクトリを
作成するために、ターミナルを開いて次のコマンドを実行してください。

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
WindowsのCMDを用いる場合は、こちらです。

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
つぎに、*main.rs*という名前でソースファイルを作成しましょう。Rustのファイルの
名前は、常に*.rs*拡張子で終わります。ファイルの名前に２つ以上の単語を使いたい
ときは、単語の区切りにアンダースコアを挟んでください。例えば、*helloworld.rs*と
するよりも*hello_world.rs*としたほうが良いでしょう。

<!--
Now open the *main.rs* file you just created and enter the code in Listing 1-1.
-->
さて、たった今作成した*main.rs*ファイルを開いて、リスト１－１の通りにコードを
入力しましょう。

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
ファイルを保存して、ターミナルのウィンドウに戻ってください。LinuxとmacOSでは、
このコマンドを入力して、このファイルをコンパイル、実行してください。

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
OSに関わらず、文字列`Hello, world!`が、ターミナルに出力されました。この通りに
出力されない場合は、インストールの節の[「トラブルシューティング」
][troubleshooting]に戻って、助けを得る方法を参照してください。

<!--
If `Hello, world!` did print, congratulations! You’ve officially written a Rust
program. That makes you a Rust programmer—welcome!
-->
`Hello, world!`が出力された方、おめでとうございます。あなたは正式にRustの
プログラムを書いたのです。晴れてあなたは、Rustプログラマの一員です。

<!--
### Anatomy of a Rust Program
-->
### Rustプログラムの解剖学

<!--
Let’s review in detail what just happened in your “Hello, world!” program.
Here’s the first piece of the puzzle:
-->
”Hello, world!”のプログラム内で何が起こったのか、詳しく見ていきましょう。今ここ
に、パズルの１つ目のピースがあります。

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
これらの行は、Rustでの関数の定義をしています。`main`関数は特別で、これは、
実行可能なRustのプログラム内で最初に走るコードです。１行目は、引数を持たず何も
返さない`main`と名付けられた関数を宣言しています。引数を取りたいときは、丸括弧
`()`の内側に書きます。

<!--
Also, note that the function body is wrapped in curly brackets, `{}`. Rust
requires these around all function bodies. It’s good style to place the opening
curly bracket on the same line as the function declaration, adding one space in
between.
-->
また、関数の本体が波括弧`{}`で囲まれていることに注意してください。Rustでは、常に
関数の中身を波括弧で囲む必要があります。関数の宣言と同じ行に、間に空白を１つ
挟んで開き波括弧を置くのは、良い書き方です。

<!--
If you want to stick to a standard style across Rust projects, you can use an 
automatic formatter tool called `rustfmt` to format your code in a particular
style. The Rust team has included this tool with the standard Rust distribution,
like `rustc`, so it should already be installed on your computer! Check the online
documentation for more details.
-->
プロジェクト全体でコードスタイルの基準に忠実にありたい場合、`rustfmt`と呼ばれる
自動整形ツールを使用することで、特定のスタイルで整形することができます。Rust
チームは、このツールを`rustc`のような標準的なRustディストリビューションに含めて
います。そのため、あなたのコンピュータには既にインストールされているはずです。
詳細については、オンラインドキュメントを参照してください。

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
この行が、この小さなプログラムの仕事のすべてをしています。これが、画面に文字を
出力します。ここには注目するべき４つの重要な要素があります。

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
２つ目に、`println!`は、Rustのマクロを呼び出します。もしこれが関数なら、
`println`（`!`無し）と表記されます。Rustのマクロは、第１９章でより詳細に扱います
。ひと先ずは、関数の代わりにマクロを呼び出すためには`!`をつける必要が有るという
ことだけ知っておいてください。

<!--
Third, you see the `"Hello, world!"` string. We pass this string as an argument
to `println!`, and the string is printed to the screen.
-->
３つ目に、文字列`"Hello, world!"`がコード中にあります。この文字列を`println!`に
引数として渡しており、これがスクリーンに出力されます。

<!--
Fourth, we end the line with a semicolon (`;`), which indicates that this
expression is over and the next one is ready to begin. Most lines of Rust code
end with a semicolon.
-->
４つ目に、この行はセミコロン（`;`）で終わっています。セミコロンはこの式が終わり
次の式が始まることを表しています。Rustのコードの行は、ほとんどがセミコロンで
終わります。

<!--
### Compiling and Running Are Separate Steps
-->
### コンパイルと実行は別のステップ

<!--
You’ve just run a newly created program, so let’s examine each step in the
process.
-->
たった今作ったプログラムを、実行してみたので、それぞれのステップを検証して
みましょう。

<!--
Before running a Rust program, you must compile it using the Rust compiler by
entering the `rustc` command and passing it the name of your source file, like
this:
-->
Rustのプログラムは、実行する前にRustコンパイラを使ってコンパイルする必要が
あります。この例のように`rustc`コマンドにソースファイルの名前を渡しましょう。

```console
$ rustc main.rs
```

<!--
If you have a C or C++ background, you’ll notice that this is similar to `gcc`
or `clang`. After compiling successfully, Rust outputs a binary executable.
-->
CやC++の経験がある人は、これが`gcc`や`clang`に似ていることに気づくかもしれません
。コンパイルに成功したら、Rustは実行可能なバイナリを出力します。

<!--
On Linux, macOS, and PowerShell on Windows, you can see the executable by
entering the `ls` command in your shell. On Linux and macOS, you’ll see two
files. With PowerShell on Windows, you’ll see the same three files that you
would see using CMD.
-->
Linux、macOS、またはWindowsのPowerShellでは、`ls`コマンドを使うことで
実行ファイルを確認することができます。LinuxとmacOSでは、２つのファイル名が
表示されます。Windowsの場合、PowerShellでは、CMDを使った例と同様に３つのファイル
が表示されます。

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
*.rs*の拡張子で始まるソースコードファイル、実行ファイル（Windowsでは*main.exe*、
他のすべての環境では*main*）、それからWindowsを使っている場合はデバッグ情報が
記述されている、拡張子が*.pdb*のファイルが表示されます。*main*または*main.exe*は
、このように実行します。

```console
$ ./main # Windowsの場合は .\main.exe
```

<!--
If *main.rs* was your “Hello, world!” program, this line would print `Hello,
world!` to your terminal.
-->
もし*main.rs*が”Hello, world!”のプログラムならば、これを実行すると`Hello, world`
がターミナルに表示されるでしょう。

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
RubyやPython、JavaScriptのような動的言語に親しんできた人は、コンパイルと実行を
別のステップに分けて行うことに慣れていないかもしれません。Rustは事前コンパイル
言語です。これは、プログラムをコンパイルしたあと、実行ファイルを他の誰かにあげる
ことができ、またそれを受け取った人は、Rustをインストールしなくても実行できること
を意味します。*.rb* や *.py*、*.js*を渡す場合、受け取る人は各々がそれぞれRubyや
Python、JavaScriptの実装をインストールする必要があります。しかし、これらの言語
では、コンパイルと実行をするために１つのコマンドしか必要としません。全ては
言語設計におけるトレードオフなのです。

<!--
Just compiling with `rustc` is fine for simple programs, but as your project
grows, you’ll want to manage all the options and make it easy to share your
code. Next, we’ll introduce you to the Cargo tool, which will help you write
real-world Rust programs.
-->
単純なプログラムであれば`rustc`でコンパイルするだけでも十分ですが、プロジェクト
が成長してくると、すべてのオプションの管理と簡単なコードの共有をしたくなって
来ます。次の節では、現実にRustでプログラムを書くことを助けてくれる、Cargoという
ツールを紹介します。

[troubleshooting]: ch01-01-installation.html#トラブルシューティング
