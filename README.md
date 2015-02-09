#TeXのメモ

##[algorithm2e.styを使った擬似コードの作成](https://github.com/Ry0/TeX_memo/tree/master/algorithm2e)
* 擬似コードを作成するためのTips  
* `algorithmic.sty`を使わない，ちょっと変わったやつ．自由度が高い．ちょっとカッコいい．

##[Sublime TextのTeXスニペット](https://github.com/Ry0/sublime-text-2/tree/master/Packages/LaTeX)
* 別レポジトリに↓
* [sublime-text-2/Packages/LaTeX/](https://github.com/Ry0/sublime-text-2/tree/master/Packages/LaTeX)

##数式関連
###数式の基本
[http://www.latex-cmd.com/equation/equation.html](http://www.latex-cmd.com/equation/equation.html)  

###ギリシャ文字
[http://nyanya.sakura.ne.jp/es/math/greek.html](http://nyanya.sakura.ne.jp/es/math/greek.html)  

###記号
数式中の特殊記号  
[http://www002.upp.so-net.ne.jp/latex/kigou_all.html](http://www002.upp.so-net.ne.jp/latex/kigou_all.html)  

以上，以下  

|意味|コマンド|
|:--|:--|
|≦|\leqq|
|≧|\geqq|

ニアイコール≒  
```tex
\fallingdotseq
```

①，②...  
```tex
\usepackage{pifont}
\ding{192}
```
いくつか例を挙げると①は192，②は193になる．  
[http://www.mlab.t.u-tokyo.ac.jp/~saru/archives/000060.php](http://www.mlab.t.u-tokyo.ac.jp/~saru/archives/000060.php)  

###数式中で文字を斜体にしない
数式のおいて，単位を書く場合は，そのまま文字を書くのではなく，
```tex
\mathrm{ }
```
の中に書く．  
[http://tex.pc-physics.com/unit.html](http://tex.pc-physics.com/unit.html)  

または数式を斜体にしないコマンド  
```tex
\rm{}
```
を使う．  
[http://www002.upp.so-net.ne.jp/latex/font_function.html](http://www002.upp.so-net.ne.jp/latex/font_function.html)  

###数式3点リーダ
|コマンド|意味|
|:--|:--|
|\cdots|横一列に三点並ぶ．点は行の中央に並ぶ．|
|\ddots|左方上がりの斜めに三点並ぶ．|
|\vdots|縦一列に三点並ぶ．|
|\ldots|横一列に三点並ぶ．点は行の下部に並ぶ．|

[http://utsukemononi.gozaru.jp/latex/datm031.html](http://utsukemononi.gozaru.jp/latex/datm031.html)

###条件わけ
[http://www.biwako.shiga-u.ac.jp/sensei/kumazawa/tex/enumerate.html](http://www.biwako.shiga-u.ac.jp/sensei/kumazawa/tex/enumerate.html)  

###なぜならマーク，ゆえにマーク
|記号|コマンド|
|:--|:--|
|∵|\since|
|∴|\therefore|


##図，表関連
###図の基本
```tex
\usepackage [dvipdfm]{graphicx}

\begin{figure}[htbp]
  \begin{center}
    \includegraphics[width=100mm]{fig1.eps}
  \end{center}
  \caption{図の説明}
  \label{fig:one}
\end{figure}
```

|位置指定|意味|
|:--|:--|
| h | 記述した場所に表を出力 |
| t | ページの上端に表を出力 |
| b | ページの下端に表を出力 |
|p | 表専用のページを用意して出力 |

[http://www.latex-cmd.com/fig_tab/figure01.html](http://www.latex-cmd.com/fig_tab/figure01.html)  
[http://hooktail.org/computer/index.php?%BF%DE%A4%CE%C1%DE%C6%FE#content_1_1](http://www.latex-cmd.com/fig_tab/figure01.html)  
[http://oku.edu.mie-u.ac.jp/~okumura/texwiki/?TeX%E5%85%A5%E9%96%80%2F%E5%9B%B3%E8%A1%A8](http://oku.edu.mie-u.ac.jp/~okumura/texwiki/?TeX%E5%85%A5%E9%96%80%2F%E5%9B%B3%E8%A1%A8)

###表組み
ラウス表  
```tex
\begin{table}[h]
  \begin{center}
    \begin{tabular}{c|cc}
      $s^2$ & $gT$ & 1+gT\\
      $s^1$ & $-2(gT-1)$ & 0\\
      $s^0$ & $\frac{-2(gT-1)(gT+1)}{-2(gT-1)}$ & 0
    \end{tabular}
  \end{center}
\end{table}
```
[http://www.latex-cmd.com/fig_tab/table01.html](http://www.latex-cmd.com/fig_tab/table01.html)  

tabular環境の中で行を縦に結合  
```tex
\usepackage{multirow}
```
[http://anchoret.seesaa.net/article/79518144.html](http://anchoret.seesaa.net/article/79518144.html)  

リスト表示  
```tex
\begin {description}
  \item[$r(k)$] : 目標値 ( 離散時間信号 )
  \item[$u(k)$] : 制御入力 ( 離散時間信号 )
  \item[$y(k)$] : 制御対象出力 (離散時間信号 )
  \item[$e(k)$] : 制御偏差 ( 離散時間信号 )
  \item[$u(t)$] : 制御入力 ( 連続時間信号 )
  \item[$y(t)$] : 制御対象出力 ( 連続時間信号 )
\end {description}
```
[http://akita-nct.jp/yamamoto/comp/latex/make_doc/item/item.php](http://akita-nct.jp/yamamoto/comp/latex/make_doc/item/item.php)  

```tex
\begin{enumerate}[{(}1{)}]
  \item 図\ref{f:実験より得られるボード線図}下段に示すように各黒丸を通る曲線をプロットする．
  \item (1)でプロットした曲線から，位相が$-45$度となる折点周波数$\omega_{d}$を求める．
  \item 図\ref{f:実験より得られるボード線図}上段において，近似ゲイン線図をプロットし，低周波数ゲイン$\overline{k}$を求める．
  \item $\omega_{d}$，$\overline{k}$の値を用いて式(5)より対象の時定数$T$とゲイン$k$を求める．
\end{enumerate}
```
もっと箇条書き等を極める↓  
[http://keizai.okomeda.net/latex/tutorial/list.html](http://keizai.okomeda.net/latex/tutorial/list.html)  

##その他，小ネタ
###図のタイトル「Figure～」を「図」に変更する
```tex
\renewcommand{\figurename}{図}
```

###図のタイトルを図{章番号}.{図番号}～にする
```tex
\renewcommand{\thefigure}{\thesection.\arabic{figure}}
```

###TeXにプログラムのソースを載せる
[http://tjun.org/blog/2008/06/latex-code/](http://tjun.org/blog/2008/06/latex-code/)  

###再レポート用のページ番号
```tex
\renewcommand{\thepage}{再\arabic{page}}
```

###空白等
指定した図を全部置いたあとリセットして文章書き始める  
```tex
\clearpage
```
[http://www.latex-cmd.com/struct/space.html](http://www.latex-cmd.com/struct/space.html)  

###章，節，表，図番号 etc...リセット
次の図の番号より1少ない値をカウンタにセット  

|項目|コマンド|
|:--|:--|
|図|\setcounter{figure}{4}|
|表|\setcounter{table}{12}|
|章|\setcounter{section}{6}|
|式|\setcounter{equation}{12}|

###EPS出力用プリンタで保存したファイルの処理
仮想プリンタ導入(Windows)  
デバイスとプリンタ  
→  
プリンタの追加  
→  
ローカル～  
→  
既存の～の「FILE～」  
→  
一番下のゼロックス  
6180N PS  
あとは適当  
これでEPS出力できる．  
印刷でこのデバイスで印刷ってやる．  
保存名は拡張子わすれずに．

###EPSのBoundingBox調整
EPSファイルを適当なテキストエディタで開いて  
上から数行目あたりの  
```bash
%%BoundingBox: (atend)
```
の記述探す．  
これを  
```bash
%%BoundingBox: 45 535 289 793
```
みたく設定する．  
45 535が左下の座標  
289 793が右上の座標  

###付録をつける
```tex
\appendix
\def\thesection{付録\Alph{section}}
\def\thesubsection{\Alph{section}\arabic{subsection}}

\makeatletter
\renewcommand{\theequation}{\Alph{section}.\arabic{equation}}
\@addtoreset{equation}{section}
\makeatother
% \setcounter{page}{1}

\section{ }
```

###外国の著者の特別なアクセント記号対策
[http://www.biwako.shiga-u.ac.jp/sensei/kumazawa/tex/accent.html](http://www.biwako.shiga-u.ac.jp/sensei/kumazawa/tex/accent.html)  