<!--
# Introduction
-->
# イントロダクション

<!-- 
> Note: This edition of the book is the same as [The Rust Programming
> Language][nsprust] available in print and ebook format from [No Starch
> Press][nsp].
-->
> お知らせ：本書のこの版は、[No Scratch][nsp]で入手できる
> [The Rust Programming Language][nsprust]（英語版）と同じ内容です。

[nsprust]: https://nostarch.com/rust
[nsp]: https://nostarch.com/

<!--
Welcome to *The Rust Programming Language*, an introductory book about Rust.
The Rust programming language helps you write faster, more reliable software.
High-level ergonomics and low-level control are often at odds in programming
language design; Rust challenges that conflict. Through balancing powerful
technical capacity and a great developer experience, Rust gives you the option
to control low-level details (such as memory usage) without all the hassle
traditionally associated with such control.
-->
*プログラミング言語Rust*へようこそ。これはRustへの入門書です。Rust言語は、高速で信頼性の高い
ソフトウェアを書く手助けをしてくれます。抽象度の高さによる扱いやすさと低レイヤーの制御は、相容れ
ないプログラミング言語の設計方針である事が多いです。しかしながら、Rustはこの問題の解決に挑戦して
います。強力な技術的能力と素晴らしい開発体験を両立させることを通して、Rustは低レイヤーの細かな
制御（メモリの管理など）を、関連する面倒ごとなしに行うための選択肢をもたらします。

<!--
## Who Rust Is For
-->
## Rustを使ってほしい人

<!--
Rust is ideal for many people for a variety of reasons. Let’s look at a few of
the most important groups.
-->
様々な理由から、Rustは多くの人にとって理想的なものであるといえます。いくつかの主要な例を見てみま
しょう。

<!--
### Teams of Developers
-->
### 開発者チーム

<!--
Rust is proving to be a productive tool for collaborating among large teams of
developers with varying levels of systems programming knowledge. Low-level code
is prone to a variety of subtle bugs, which in most other languages can be
caught only through extensive testing and careful code review by experienced
developers. In Rust, the compiler plays a gatekeeper role by refusing to
compile code with these elusive bugs, including concurrency bugs. By working
alongside the compiler, the team can spend their time focusing on the program’s
logic rather than chasing down bugs.
-->
Rustは、異なる能力の開発者が大きなチームで協力して開発することを、より生産的にしてくれるツール
です。低レイヤーのコードは、様々な種類の微小なバグが発生しやすく、他のほとんどのプログラミング言語
では、網羅的なテストと経験豊富な人によるコードレビューを行うことでしか、そのようなバグを発見する
ことはできませんでした。一方Rustでは、この様に発見しづらかったり、並列処理に伴って発生したりする
バグを、コンパイラーが拒否します。さながら門番のようですね。コンパイラーを活用することで、
バグの追跡ではなくプログラムのロジックに集中できるようになります。

<!--
Rust also brings contemporary developer tools to the systems programming world:
-->
Rustは、システムプログラミングの世界に現代的な開発ツールをもたらします。

<!--
* Cargo, the included dependency manager and build tool, makes adding,
  compiling, and managing dependencies painless and consistent across the Rust
  ecosystem.
* Rustfmt ensures a consistent coding style across developers.
* The Rust Language Server powers Integrated Development Environment (IDE)
  integration for code completion and inline error messages.
-->
* Cargoという依存関係マネージャー兼ビルドツールがRustには付属しています。Cargoは、依存関係
  の追加、コンパイル及び管理を容易にしてくれます。Cargoのおかげで、Rustのエコシステムは一貫性の
  とれたものになっています。
* Rustfmtは、開発者間でコーディングスタイルを統一する簡単な方法を提供してくれます。
* Rust Language Serverは、統合開発環境（IDE）がコード補完やインラインエラーメッセージを提供
  できるようにしてくれます。

<!--
By using these and other tools in the Rust ecosystem, developers can be
productive while writing systems-level code.
-->
Rustのエコシステムに則ってこれらのツールを使用すれば、システムレベルのコードを生産性を保ちながら
書くことができるでしょう。

<!--
### Students
-->
### 学生

<!--
Rust is for students and those who are interested in learning about systems
concepts. Using Rust, many people have learned about topics like operating
systems development. The community is very welcoming and happy to answer
student questions. Through efforts such as this book, the Rust teams want to
make systems concepts more accessible to more people, especially those new to
programming.
-->
Rustは、システムの概念を学ぶことに興味を持つ学生にとって、良い選択となるでしょう。多くの人が、
Rustを使ってOSの開発などを学んでいます。コミュニティーは学生の皆さんを歓迎しており、質問にも喜ん
で答えてくれるでしょう。Rustチームはこの入門書の執筆などの取り組みを通して、システムの概念を、
プログラミング初心者も含むより多くの人にとって身近なものにしたいと考えています。

<!--
### Companies
-->
### 企業

<!--
Hundreds of companies, large and small, use Rust in production for a variety of
tasks. Those tasks include command line tools, web services, DevOps tooling,
embedded devices, audio and video analysis and transcoding, cryptocurrencies,
bioinformatics, search engines, Internet of Things applications, machine
learning, and even major parts of the Firefox web browser.
-->
大小を問わず何百もの企業が、様々な製品にRustを使用しています。これらの製品には、コマンドライン
ツールやWebサービス、DevOpsツール、組み込み端末、音声及び画像の分析と処理、暗号通貨、
生命情報科学、検索エンジン、IoTアプリケーション、機械学習そしてWebブラウザーのFirefoxなどが
あります。

<!--
### Open Source Developers
-->
### OSS開発者

<!--
Rust is for people who want to build the Rust programming language, community,
developer tools, and libraries. We’d love to have you contribute to the Rust
language.
-->
Rustは、Rust言語やそのコミュニティー、開発者ツールそしてライブラリーなどを開発したいと考えている
人たちにとっても有用です。私たちは、皆さんがRust言語の発展に寄与してくれることを期待しています。

<!--
### People Who Value Speed and Stability
-->
### 速度と安定性を重視する人

<!--
Rust is for people who crave speed and stability in a language. By speed, we
mean the speed of the programs that you can create with Rust and the speed at
which Rust lets you write them. The Rust compiler’s checks ensure stability
through feature additions and refactoring. This is in contrast to the brittle
legacy code in languages without these checks, which developers are often
afraid to modify. By striving for zero-cost abstractions, higher-level features
that compile to lower-level code as fast as code written manually, Rust
endeavors to make safe code be fast code as well.
-->
Rustは、プログラミング言語に速度と安定性を求めている人々にとっても良い言語です。速度というのは、
Rustによって生成できるプログラムの実行速度とプログラムを書く速度の両方のことを指します。Rustの
コンパイラーのチェックは、機能の追加やリファクタリングを安定して行えることを保証します。これは、
こういったチェックを行わない言語で書かれていて脆弱な、修正をするのも恐ろしいレガシーコードとは
対照的です。またRustは、安全性と速度を両立するコードを実現するために、ゼロコストの抽象化を追求
しています。このおかげで、自ら低レイヤーでコードを書くのと同程度に速いコードを書くことができます。

<!--
The Rust language hopes to support many other users as well; those mentioned
here are merely some of the biggest stakeholders. Overall, Rust’s greatest
ambition is to eliminate the trade-offs that programmers have accepted for
decades by providing safety *and* productivity, speed *and* ergonomics. Give
Rust a try and see if its choices work for you.
-->
ここに挙げた人たちは、最大の利害関係者のうちのほんの一部でしかありません。Rust言語は、これ以外に
も多くのユーザーをサポートしたいと考えています。Rustが全てにおいて目指していることは、
プログラマーが数十年に渡って甘受してきたトレードオフを取り払うことです。この目的を達成するために
、安全*かつ*生産的そして高速*かつ*扱いやすいプログラミング言語を提供しようとしています。

<!--
## Who This Book Is For
-->
## 本書の想定読者

<!--
This book assumes that you’ve written code in another programming language but
doesn’t make any assumptions about which one. We’ve tried to make the material
broadly accessible to those from a wide variety of programming backgrounds. We
don’t spend a lot of time talking about what programming *is* or how to think
about it. If you’re entirely new to programming, you would be better served by
reading a book that specifically provides an introduction to programming.
-->
本書は、読者が他のプログラミング言語でコードを書いたことがあることを前提に書かれていますが、どの
プログラミング言語かということは一切仮定していません。私たちは、多種多様なプログラミングの経歴を
持つ誰であっても広く理解できるように、努めています。プログラミングとは何か、あるいはプログラミング
のための思考法についてなどにはあまり言及しません。もしあなたが全くのプログラミング初心者であるなら
ば、本書とは別にプログラミングへの具体的な導入をしてくれる本を読んだほうがいいでしょう。

<!--
## How to Use This Book
-->
## 本書の活用方法

<!--
In general, this book assumes that you’re reading it in sequence from front to
back. Later chapters build on concepts in earlier chapters, and earlier
chapters might not delve into details on a topic; we typically revisit the
topic in a later chapter.
-->
本書は、始めから順番に読むことを想定して執筆されています。あとの章は、前の章で紹介した概念を既
に知っているものとして書かれます。また、その場では詳細を掘り下げずに話を進めることがありますが、
その場合には、基本的にあとの章で改めて確認します。

<!--
You’ll find two kinds of chapters in this book: concept chapters and project
chapters. In concept chapters, you’ll learn about an aspect of Rust. In project
chapters, we’ll build small programs together, applying what you’ve learned so
far. Chapters 2, 12, and 20 are project chapters; the rest are concept chapters.
-->
本書には、コンセプトの章とプロジェクトの章の二種類の章があります。コンセプトの章では、Rustの特徴
を学びます。プロジェクトの章では、そこまでで学んだ内容を踏まえて小さなプログラムを書いてみます。
第２章、第１２章、及び第２０章はプロジェクトの章で、それ以外はコンセプトの章です。

<!--
Chapter 1 explains how to install Rust, how to write a “Hello, world!” program,
and how to use Cargo, Rust’s package manager and build tool. Chapter 2 is a
hands-on introduction to the Rust language. Here we cover concepts at a high
level, and later chapters will provide additional detail. If you want to get
your hands dirty right away, Chapter 2 is the place for that. At first, you
might even want to skip Chapter 3, which covers Rust features similar to those
of other programming languages, and head straight to Chapter 4 to learn about
Rust’s ownership system. However, if you’re a particularly meticulous learner
who prefers to learn every detail before moving on to the next, you might want
to skip Chapter 2 and go straight to Chapter 3, returning to Chapter 2 when
you’d like to work on a project applying the details you’ve learned.
-->
第１章は、Rustのインストール方法、ハローワールド、そしてRustにおけるパッケージマネージャー兼
ビルドツールであるCargoの使い方を説明します。第２章は、Rust言語への実践的な導入です。この章では
Rustのコンセプトを大まかに学びます。より詳細な説明はこれよりあとの章で行います。第２章は、今すぐ
にRustで何かを作ってみたいという方にうってつけです。第３章は、他のプログラミング言語でもよく
取り入れられている機能を紹介しています。この章を飛ばして、Rust特有の所有権システムについて説明し
ている第４章を先に読むのもいいでしょう。しかしもし、あなたが詳細を理解することに重点を置く几帳面
な初心者であるならば、先に第３章を読んでから第２章に戻ってくるほうが良いかもしれません。

<!--
Chapter 5 discusses structs and methods, and Chapter 6 covers enums, `match`
expressions, and the `if let` control flow construct. You’ll use structs and
enums to make custom types in Rust.
-->
第５章では構造体とメソッドを、第６章では列挙型、`match`式そして`if let`というフロー制御のため
の構文を紹介します。Rustでは、構造体と列挙型を組み合わせることで独自の型を作ることができます。

<!--
In Chapter 7, you’ll learn about Rust’s module system and about privacy rules
for organizing your code and its public Application Programming Interface
(API). Chapter 8 discusses some common collection data structures that the
standard library provides, such as vectors, strings, and hash maps. Chapter 9
explores Rust’s error-handling philosophy and techniques.
-->
第７章では、Rustのモジュールシステムと、コードや公開のAPI（Application Programming
Interface）を管理するためのプライバシールールについて学びます。第８章では、配列や文字列、
ハッシュマップなど、標準ライブラリーが提供する構造体の内のいくつかを紹介します。第９章では、Rust
のエラーハンドリングにおける考え方と方法について探求します。

<!--
Chapter 10 digs into generics, traits, and lifetimes, which give you the power
to define code that applies to multiple types. Chapter 11 is all about testing,
which even with Rust’s safety guarantees is necessary to ensure your program’s
logic is correct. In Chapter 12, we’ll build our own implementation of a subset
of functionality from the `grep` command line tool that searches for text
within files. For this, we’ll use many of the concepts we discussed in the
previous chapters.
-->
第１０章では、異なる複数の型に適用できるコードを定義するための機能であるジェネリクス、トレイト、
ライフタイムを掘り下げます。第１１章では、その紙幅丸々をテストの話題に費やします。Rustの安全性は
保証されていますがそれでも、プログラムロジックが正しいことを保証するために、テストは必要です。
第１２章では、ファイル内のテキストを検索するためのコマンドラインツールである`grep`と同様の機能の
一部を、独自に実装してみます。この章では、そこまでで説明した概念の多くを使用します。

<!--
Chapter 13 explores closures and iterators: features of Rust that come from
functional programming languages. In Chapter 14, we’ll examine Cargo in more
depth and talk about best practices for sharing your libraries with others.
Chapter 15 discusses smart pointers that the standard library provides and the
traits that enable their functionality.
-->
第１３章では、関数型プログラミング言語に由来するクロージャーとイテレーターについて理解します。
第１４章では、Cargoについてより深くまで学んだ後、自作ライブラリーを共有する最善の方法を紹介し
ます。第１５章では、標準ライブラリーが提供し、トレイトによって実現されているスマートポインター
を紹介します。

<!--
In Chapter 16, we’ll walk through different models of concurrent programming
and talk about how Rust helps you to program in multiple threads fearlessly.
Chapter 17 looks at how Rust idioms compare to object-oriented programming
principles you might be familiar with.
-->
第１６章では、並列プログラミングの様々な形式を学びながら、マルチスレッドでのプログラミングを安全
に行うことをRustがどのように手伝ってくれるかを学びます。第１７章では、みなさんが親しんできたで
あろうオブジェクト指向プログラミング言語とRustを、その書き方の観点から比較します。

<!--
Chapter 18 is a reference on patterns and pattern matching, which are powerful
ways of expressing ideas throughout Rust programs. Chapter 19 contains a
smorgasbord of advanced topics of interest, including unsafe Rust, macros, and
more about lifetimes, traits, types, functions, and closures.
-->
第１８章では、Rustであなたのアイデアを表現するための強力な方法である、パターン、そしてパターン
マッチングについて言及します。第１９章には、マクロや安全性が保証されないRustの書き方、他にも
ライフタイムやトレイト、型、関数、クロージャーについての発展的な話題がいくつも含まれています。

<!--
In Chapter 20, we’ll complete a project in which we’ll implement a low-level
multithreaded web server!
-->
そして第２０章では、マルチスレッドで動くWebサーバーを低レイヤーで実装します。

<!--
Finally, some appendices contain useful information about the language in a
more reference-like format. Appendix A covers Rust’s keywords, Appendix B
covers Rust’s operators and symbols, Appendix C covers derivable traits
provided by the standard library, Appendix D covers some useful development
tools, and Appendix E explains Rust editions.
-->
巻末には、いくつかの付録があります。ここにはRust言語についての有用な情報が、リファレンスに近い
形式で載っています。付録ＡにはRustのキーワード、付録ＢにはRustの演算子とシンボル、付録Ｃには
標準ライブラリーのトレイト、付録Ｄには便利な開発ツール、そして付録ＥにはRustのエディション
についての情報が、それぞれ掲載されています。

<!--
There is no wrong way to read this book: if you want to skip ahead, go for it!
You might have to jump back to earlier chapters if you experience any
confusion. But do whatever works for you.
-->
本書をどのように読んでも、間違いということはありませんから、読み飛ばしたいと思う章は、飛ばしても
らって構いません。前の章を読み返さなければ理解しづらいこともあるかもしれませんが、自分に都合のいい
ように読むのが一番でしょう。

<span id="ferris"></span>

<!--
An important part of the process of learning Rust is learning how to read the
error messages the compiler displays: these will guide you toward working code.
As such, we’ll provide many examples that don’t compile along with the error
message the compiler will show you in each situation. Know that if you enter
and run a random example, it may not compile! Make sure you read the
surrounding text to see whether the example you’re trying to run is meant to
error. Ferris will also help you distinguish code that isn’t meant to work:
-->
Rustを学ぶ上で特に重要なことは、コンパイラーが出力するエラーメッセージの読み方を知ることです。
エラーメッセージは、コードを正常に動作する方法を教えてくれます。エラーメッセージの読み方を知って
もらうために、コンパイルできないコードの例をコンパイラーが出力するエラーメッセージとともに掲載する
ことがあります。そのため、例を適当に選んで実行しようとしたらコンパイルできなかった、ということが
起こりうることに気をつけてください。必ず周囲の文章を確認して、実行しようとしているコードがエラーに
なることを予期して例示されているものかどうかを確認してください。フェリスは、そのコードが動くかどう
かを見分ける手伝いをしてくれます。

<!--
| Ferris                                                                 | Meaning                                          |
|------------------------------------------------------------------------|--------------------------------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain"/>    | This code does not compile!                      |
| <img src="img/ferris/panics.svg" class="ferris-explain"/>              | This code panics!                                |
| <img src="img/ferris/unsafe.svg" class="ferris-explain"/>              | This code block contains unsafe code.            |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain"/>| This code does not produce the desired behavior. |
-->
| フェリス                                                                 | 意味                        |
|------------------------------------------------------------------------|-----------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain"/>    | コンパイルできないよ！          |
| <img src="img/ferris/panics.svg" class="ferris-explain"/>              | 実行に失敗（パニック）するよ！    |
| <img src="img/ferris/unsafe.svg" class="ferris-explain"/>              | 安全じゃないコードが含まれているよ |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain"/>| 想定通りに動かないよ            |

<!--
In most situations, we’ll lead you to the correct version of any code that
doesn’t compile.
-->
多くの場合、コンパイルできないものを修正した後のコードも、みなさんに紹介しています。

<!--
## Source Code
-->
## ソースコード

<!--
The source files from which this book is generated can be found on
[GitHub][book].
-->
本書のソースファイルは[GitHub][book]で確認できます。（英語版）

[book]: https://github.com/rust-lang/book/tree/master/src

[book-ja]: https://github.com/misogohan/book/tree/master/src

> 注：この日本語訳のソースコードは、[こちらのリポジトリ][book-ja]で確認できます。