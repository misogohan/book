<!--
# Foreword
-->
# まえがき

<!--
It wasn’t always so clear, but the Rust programming language is fundamentally
about *empowerment*: no matter what kind of code you are writing now, Rust
empowers you to reach farther, to program with confidence in a wider variety of
domains than you did before.
-->
明確に実感できるようになるのは先のことかもしれませんが、Rustの根本的な目的は
*力を授けること*です。どのような分野のコードを書くときであっても、自信を持って
プログラミングをすることができるようになります。

<!--
Take, for example, “systems-level” work that deals with low-level details of
memory management, data representation, and concurrency. Traditionally, this
realm of programming is seen as arcane, accessible only to a select few who
have devoted the necessary years learning to avoid its infamous pitfalls. And
even those who practice it do so with caution, lest their code be open to
exploits, crashes, or corruption.
-->
メモリ管理やデータ表現、並列処理を低レイヤで扱う「システムレベル」の
プログラミングを例に取って見ましょう。伝統的に、悪名高い落とし穴を避けるための
学習に必要な年数を捧げてきた少数の選ばれし者にのみ可能なものとされています。また
そういう人であっても、悪用やクラッシュ、データの破損が起きないように、細心の
注意を払ってプログラミングをしなければなりません。

<!--
Rust breaks down these barriers by eliminating the old pitfalls and providing a
friendly, polished set of tools to help you along the way. Programmers who need
to “dip down” into lower-level control can do so with Rust, without taking on
the customary risk of crashes or security holes, and without having to learn
the fine points of a fickle toolchain. Better yet, the language is designed to
guide you naturally towards reliable code that is efficient in terms of speed
and memory usage.
-->
Rustは、典型的な危険性を排除し、洗練された使いやすいツール群を提供することに
よって、これらの障壁を取り除きます。専門外のプログラマがやむなく低レイヤのコード
を触る場合でもRustを使えば、頻繁に変更が加えられるツールチェインについて詳しく
学ぶ必要なしに作業を行うことができます。それだけでなく、Rustは、信頼性の高い
コードを実行速度とメモリの効率を損なうことなく自然に書けるように設計されています
。

<!--
Programmers who are already working with low-level code can use Rust to raise
their ambitions. For example, introducing parallelism in Rust is a relatively
low-risk operation: the compiler will catch the classical mistakes for you. And
you can tackle more aggressive optimizations in your code with the confidence
that you won’t accidentally introduce crashes or vulnerabilities.
-->
既に低レイヤのコードを書いているプログラマであれば、Rustを使うことでより良い
コードを書けるようになります。例えば並列処理をRustで書くことは、相対的に低リスク
な選択です。コンパイラは、並列処理でありがちなミスを発見してくれます。これに
よって、意図しないクラッシュや脆弱性を引き起こすことがないという自信をもって、
積極的にコードの最適化を行えます。

<!--
But Rust isn’t limited to low-level systems programming. It’s expressive and
ergonomic enough to make CLI apps, web servers, and many other kinds of code
quite pleasant to write — you’ll find simple examples of both later in the
book. Working with Rust allows you to build skills that transfer from one
domain to another; you can learn Rust by writing a web app, then apply those
same skills to target your Raspberry Pi.
-->
加えて、低レイヤのシステムプログラミングだけでなく、CLIアプリケーションや
Webサーバー、他にも多くのものを非常に快適に書ける、直感的な扱いやすさと表現力を
備えています。システムプログラミングもそうでないものも、簡単な例を後々紹介します
。Rustを使用すると、異なる分野を行き来するスキルを得ることができます。例えば、
Webアプリを書きながらRustを習得した後、同じスキルを使ってRaspberry Piのための
コードを書くなどです。

<!--
This book fully embraces the potential of Rust to empower its users. It’s a
friendly and approachable text intended to help you level up not just your
knowledge of Rust, but also your reach and confidence as a programmer in
general. So dive in, get ready to learn—and welcome to the Rust community!
-->
本書では、Rustがユーザーに力を与える可能性を最大限に紹介しています。Rustについて
の知識だけでなく、プログラマとしての総合的で広い視野、そして自信を持ってもらう
ことを目的としており、そのために、親しみやすい文章を心がけています。さあ、今こそ
Rustの理解への第一歩を踏み出しましょう。そしてRustコミュニティへようこそ！

<!--
— Nicholas Matsakis and Aaron Turon
-->
—　ニコラス・マサキス, アーロン・チューロン
