#algorithm2eを使った擬似コードの作成
##サイトから必要なファイルを取ってくる
###algorithm2e.styを入手．また使い方やサンプルも中に入ってる．
[http://www.ctan.org/tex-archive/macros/latex/contrib/algorithm2e](http://www.ctan.org/tex-archive/macros/latex/contrib/algorithm2e)  
![Download](./img/Download.png)  

###jdummy.defを入手
[http://shimizus.hustle.ne.jp/wiki/wiki.cgi?page=Font+shape+undefined%A5%A8%A5%E9%A1%BC%C2%D0%BD%E8](http://shimizus.hustle.ne.jp/wiki/wiki.cgi?page=Font+shape+undefined%A5%A8%A5%E9%A1%BC%C2%D0%BD%E8)  
これがないと，Sublime TextのLaTeXToolsを使った環境では，以下のWarningが  

```bash
./algorithm2e_test.tex:30: LaTeX Font Warning: Font shape `JT2/gt/m/it'    undefined(Font) using `JT2/gt/m/n' instead on input line 30.
./algorithm2e_test.tex:30: LaTeX Font Warning: Font shape `JY2/gt/m/it'    undefined(Font) using `JY2/gt/m/n' instead on input line 30.
./algorithm2e_test.tex: LaTeX Font Warning: Some font shapes were not available, defaults substituted.
```

このサイトのエラーでは`JY1/gt/m/i`が〜って言っているが，こちらでは`JY2`と`JT2`なのでダウンロードしてきた`jdummy.def`の中の，`JY1`と`JT1`の記述をそれぞれ`JY2`と`JT2`に全部置換．これでうまくいった．

##実際にコンパイルしてみる

```tex
\usepackage[ruled,vlined]{algorithm2e}
\usepackage{setspace}
\input{jdummy.def}
```

これらを記述しておく．`\usepackage[ここはレイアウトのオプション]{algorithm2e}`の`[]`はオプションを書くところ．`algorithm2e.sty`が入っていたzipのドキュメントを見る．

![成功](./img/Sample.png)  