<!--
# The Rust Programming Language
-->
# プログラミング言語 Rust

<!--
*by Steve Klabnik and Carol Nichols, with contributions from the Rust Community*
-->
*著：スティーブ・クラブニク、キャロル・ニックホールズ　協力：Rustコミュニティ*

<!--
This version of the text assumes you’re using Rust 1.48 or later with
`edition="2018"` in *Cargo.toml* of all projects to use Rust 2018 Edition
idioms. See the [“Installation” section of Chapter 1][install] to install or
update Rust, and see the new [Appendix E][editions]for information on editions.
-->
この版の本書は、Rust 2018 Editionの書き方に基づいて書かれているため、Rust 1.48かそれ以降の
Rustを使用し、すべてのプロジェクトで*Cargo.toml*ファイル内に `edition="2018"`と記載されて
いることを確認してください。Rustのインストール・更新は、[第１章「インストール」][install]に
則って行ってください。エディションについての詳細は[付録Ｅ][editions]を参照してください。

<!--
The 2018 Edition of the Rust language includes a number of improvements that
make Rust more ergonomic and easier to learn. This iteration of the book
contains a number of changes to reflect those improvements:
-->
Rust 2018 Editionでは、Rustをより学習しやすくまた直感的に扱えるようにしてくれる、いくつもの
改善がなされています。この変更にしたがって、次に挙げる章は大きく変更されています。

<!--
- Chapter 7, “Managing Growing Projects with Packages, Crates, and Modules,”
  has been mostly rewritten. The module system and the way paths work in the
  2018 Edition were made more consistent.
- Chapter 10 has new sections titled “Traits as Parameters” and “Returning
  Types that Implement Traits” that explain the new `impl Trait` syntax.
- Chapter 11 has a new section titled “Using `Result<T, E>` in Tests” that
  shows how to write tests that use the `?` operator.
- The “Advanced Lifetimes” section in Chapter 19 was removed because compiler
  improvements have made the constructs in that section even rarer.
- The previous Appendix D, “Macros,” has been expanded to include procedural
  macros and was moved to the “Macros” section in Chapter 19.
- Appendix A, “Keywords,” also explains the new raw identifiers feature that
  enables code written in the 2015 Edition and the 2018 Edition to interoperate.
- Appendix D is now titled “Useful Development Tools” and covers recently
  released tools that help you write Rust code.
- We fixed a number of small errors and imprecise wording throughout the book.
  Thank you to the readers who reported them!
-->
- 第７章「パッケージ、クレート及びモジュールによる成長するプロジェクトの管理」は、ほとんどが
  書き直されています。2018 Editionからのモジュールシステムとパスの仕組みは、より高い一貫性を
  持つようになりました。
- 第１０章には「引数としてのトレイト」と「トレイトを実装している型の返却」という節が追加されまし
  た。これらの節では、新しく追加された`impl Trait`構文について解説しています。
- 第１１章には「`Result<T, E>`のテストでの使用」という節が追加されました。この節では`?`演算子
  を使ってテストを書く方法を紹介しています。
- 第１９章の「発展的なライフタイム」という節は削除されました。コンパイラの改善によって、この節に
  あったような書き方は滅多にされなくなったためです。
- もともと付録Ｄとして載っていた「マクロ」は、手続き的マクロの解説も含むようになり、また第１９章
  に移されました。
- 付録Ａ「キーワード」では、生識別子（raw identifier 適切な訳語求む）という新しい機能について
  も解説されるようになりました。この機能は、2015 Editionと2018 Editionそれぞれの書き方で
  書かれたコードを同時に使用できるようにしてくれます。
- 付録Ｄは「有用な開発ツール」という内容になりました。Rustのコードを書くときに便利なツールを紹介
  しています。
- 他にも細かな訂正がいくつかありました。報告してくださった方々はありがとうございました。

<!--
Note that any code in earlier iterations of *The Rust Programming Language*
that compiled will continue to compile without `edition="2018"` in the
project’s *Cargo.toml*, even as you update the Rust compiler version you’re
using. That’s Rust’s backward compatibility guarantees at work!
-->
Rustコンパイラのバージョンを上げても、プロジェクト内の*Cargo.toml*に`edition="2018"`を
書かなければ、以前の版で本書に掲載されていたコードをコンパイルできます。Rustの後方互換性は維持
されています。

<!--
The HTML format is available online at
[https://doc.rust-lang.org/stable/book/](https://doc.rust-lang.org/stable/book/)
and offline with installations of Rust made with `rustup`; run `rustup docs
--book` to open.
-->
HTML形式は、
[https://doc.rust-lang.org/stable/book/](https://doc.rust-lang.org/stable/book/)
がオンラインで利用可能です。オフラインで開きたい場合は、Rustのインストール時にインストールされる
`rustup`を用いて、`rustup docs --book`を実行してください。（どちらも英語版）

<!--
This text is available in [paperback and ebook format from No Starch
Press][nsprust].
-->
本書は、紙と電子の両方の形式（英語版）が[No Scratch Press][nsprust]で入手可能です。

[install]: ch01-01-installation.html
[editions]: appendix-05-editions.html
[nsprust]: https://nostarch.com/rust
