---
layout: docs
title: VisualStudio10を使ってのビルド方法
---

VisualStudio10が既にインストールされている前提で説明します。

2.  Mercurialのインストール

    [Mercurial SCM](http://mercurial.selenic.com/)からMercurialをインストールします。

3.  ソース取得

    コマンドプロンプトから以下を実行します。
        hg clone https://vim.googlecode.com/hg/ vim

4.  コンパイル

    `vim/src`フォルダに移動し以下のコマンドを実行します。

        nmake -f Make_mvc.mak GUI=yes IME=yes MBYTE=yes
          ICONV=yes DEBUG=no

    ※実際は1行

    もしPerl拡張やRuby拡張、Python拡張を使う場合は以下の様に指定します。

        nmake -f Make_mvc.mak GUI=yes IME=yes MBYTE=yes
          ICONV=yes PERL=C:\strawberry\perl DYNAMIC_PERL=yes
          PERL_VER=512 PYTHON=c:\python27 DYNAMIC_PYTHON=yes
          PYTHON_VER=27 RUBY=c:\ruby193 DYNAMIC_RUBY=yes RUBY_VER=19
          RUBY_VER_LONG=1.9.1 CSCOPE=yes MSVCVER=6.0 NETBEANS=yes
          DEBUG=no

    ※実際は1行  
    必要に応じてビルド前に`vcvarsall.bat`や`vcvars32.bat`等を実行しておいて下さい。

