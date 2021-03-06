BXjscls パッケージバンドル
==========================

LaTeX: 全エンジン対応日本語文書クラス集

奥村晴彦氏作製の [pLaTeX2e 新ドキュメントクラス] の和文文書クラス集を
拡張したもの。元のクラスは (u)pLaTeX 専用であるが、こちらは pdfLaTeX /
XeLaTeX / LuaLaTeX の上でも日本語処理パッケージと連携して使用すること
ができる。

[pLaTeX2e 新ドキュメントクラス]:
(http://oku.edu.mie-u.ac.jp/~okumura/jsclasses/)

### 前提環境

  * TeX エンジン： pdfTeX / XeTeX / LuaTeX / pTeX / upTeX
      - e-TeX 拡張は必須でない
      - XeTeX は 0.997 版以降が必要
  * フォーマット： LaTeX
  * DVI ウェア： 不問
  * 必須パッケージ：
      - keyval
      - calc
      - geometry
  * standard 和文ドライバで連携するパッケージ：
      - (pdf)LaTeX の場合： 
        CJK / bxcjkjatype（v0.2c以降）
      - XeLaTeX の場合： 
        xeCJK（v3.0以降） / zxjatype（v0.6以降）
      - LuaLaTeX の場合： 
        LuaTeX-ja
  * その他、場合により必須となるパッケージ：
      - type1cm ： `magstyle` が `real`/`xreal` である場合
      - pxchfon（v0.5以降）： pLaTeX で `jafont` を指定した場合
      - zxjafont（v0.2a以降）： XeLaTeX で `jafont` を指定した場合
  * エンジンが (u)pTeX 以外で、かつ和文ドライバが standard 以外の場合、
    そのエンジンに対応する日本語処理パッケージが必要となる。

### 構成物

  * `bxjscls-manual.pdf`： ユーザ向け説明書
  * `bxjscls-manual.tex`： 上項のソースファイル
  * `bxjscls.dtx`： DocStrip ソースファイル
  * `bxjscls.ins`： DocStrip インストーラファイル
  * `bxjscls.pdf`： DocStrip 文書（ソースコード説明書）

※アーカイブ中に DocStrip からの生成ファイル（`*.cls`／`*.def`、一覧は
次節に後掲）が含まれる場合もある。

### インストール

本パッケージバンドルは DocStrip 形式ファイルの形で提供されている。

アーカイブに文書クラスファイル（`*.cls`／`*.def`）が含まれていない場合
は、以下のコマンドを実行して生成する。

    luatex bxjscls.ins

このコマンドにより次のファイル群が生成される。

  * `bxjsarticle.cls`： BXJS版 article クラスファイル
  * `bxjsbook.cls`： BXJS版 book クラスファイル
  * `bxjsreport.cls`： BXJS版 report クラスファイル
  * `bxjsslide.cls`： BXJS版 slide クラスファイル
  * `bxjsja-minimal.def`： minimal 和文ドライバファイル
  * `bxjsja-standard.def`： standard 和文ドライバファイル

その後、各ファイルを次の場所に移動する。
（TDS 1.1 に従ったシステムの場合。）

  - `*.cls`/`*.def` → $TEXMF/tex/latex/bxjscls/
  - `*.dtx`/`*.ins` → $TEXMF/source/latex/bxjscls/
  - `*.pdf`/`*.tex` → $TEXMF/doc/latex/bxjscls/

その後、（必要に応じて）`mktexlsr` を実行する。

#### （参考）説明書文書のコンパイル

アーカイブに含まれる説明書の PDF 文書は以下のコマンドによって生成
されたものである。

  * `bxjscls-manual.pdf` ← `lualatex bxjscls-manual.tex`
  * `bxjscls.pdf` ← `lualatex bxjscls.dtx`

### 使用方法

ユーザ向け説明書 `bxjscls-manual.pdf` を参照されたい。

### ライセンス

修正BSDライセンス（The BSD 2-Clause License）の下で配布される。

更新履歴
--------

  * Version 1.0  [2015/08/05]
      - bxjsreport と bxjsslide クラスを提供する。
      - `jafont` オプションを追加。
      - `nopapersize` オプションを追加。
      - hyperref 対策を追加。
      - microtype 対策を追加。
      - `\ifdraft` の定義を遅延させる。
      - その他もろもろ。
  * Version 0.9  [2013/10/03]
      - LuaTeX-ja との連携をサポート。
      - `magstyle`、`(no)zw`、`(no)js` オプションを追加。
      - “和文ドライバ”の概念を採用して、ソースコードの構成を
        大幅に変更した。
  * Version 0.4  [2013/08/03]
      - CJK + bxcjkjatype との連携を追加。
  * Version 0.3a [2012/05/01]
      - 一部の用紙サイズオプション（`b4paper` 等）で、縦と横の長さを
        逆に指定していたのを修正した。
  * Version 0.3  [2010/08/15]
      - (u)pLaTeX 用連携モジュールを追加。
      - `jbase` クラスオプションを追加。
      - `base`, `jbase`, `mag` を calc パッケージの数式で
        記述できるようにした。
  * Version 0.2  [2009/08/15]
      - 最初の公開版。

--------------------
Takayuki YATO (aka. "ZR")  
http://zrbabbler.sp.land.to/
