# 課題７
画像処理工学

　画素のダイナミックレンジを０から２５５にせよ．

１．	使用プログラム


filename = uigetfile('*');

ORG=imread(filename);  % 画像の読み込み

ORG = rgb2gray(ORG); % 白黒濃淡画像に変換

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;

imhist(ORG); % 濃度ヒストグラムを生成、表示

pause;

ORG = double(ORG); % この行について考察せよ

mn = min(ORG(:)); % 濃度値の最小値を算出

mx = max(ORG(:)); % 濃度値の最大値を算出

ORG = (ORG-mn)/(mx-mn)*255;

imagesc(ORG); colormap(gray); colorbar; % 画像の表示

pause;

ORG = uint8(ORG); % この行について考察せよ

imhist(ORG); % 濃度ヒストグラムを生成、表示



 
２．	実行結果
 
 ![原画像](https://github.com/enazii0312/image/blob/master/a.jpg)
 
図１　原画像のグレースケール(273×185)

  ![原画像](https://github.com/enazii0312/image/blob/master/c.jpg)
  
図２　原画像の濃度ヒストグラム
 
  ![原画像](https://github.com/enazii0312/image/blob/master/d.jpg)
  
図３　ダイナミックレンジ拡大後のグレースケール

  ![原画像](https://github.com/enazii0312/image/blob/master/e.jpg)
  
図４　ダイナミックレンジ拡大後の濃度ヒストグラム

３．	考察
　今回の課題は画像のダイナミックレンジを0~255に拡大し、拡大前のヒストグラムと比較を行うものであった。今回の課題の場合のダイナミックレンジとは白と黒の表現可能範囲を指す。
ダイナミックレンジを拡大する前の最小値、最大値は以下の様になった。

  ![原画像](https://github.com/enazii0312/image/blob/master/f.jpg)
  
図５　ダイナミックレンジ拡大前の最小値、最大値

ダイナミックレンジ拡大後の最小値、最大値は以下の様になり、0~255に拡大できた事が確認できる。

  ![原画像](https://github.com/enazii0312/image/blob/master/g.jpg)
  
図６　ダイナミックレンジ拡大後の最小値、最大値

図１、図３を比較しても変化した様子は劇的には確認しにくいが濃度ヒストグラムの図２、図４を比較すると図２ではまとまっていたヒストグラムが図４では広がり、所々に目視できる隙間が確認できた。
これが起きた原因はORGの値が拡大前は少数値が扱えるdoubleであったのに対して拡大後は整数表示のuint8で表現されているため少数の丸めが起こり、隙間が生まれたと考えられる。
以下にORGのdouble値とuint8値の結果を記す。

  ![原画像](https://github.com/enazii0312/image/blob/master/h.jpg)
  
図７　ORGのdouble値

  ![原画像](https://github.com/enazii0312/image/blob/master/i.jpg)
  
図８　ORGのuint8値
