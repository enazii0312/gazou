# 課題２
画像処理工学

２階調，４階調，８階調の画像を生成せよ．

１．	使用プログラム

clear; % 変数のオールクリア 
 
 filename = uigetfile('*');
 
 ORG=imread(filename); % 原画像の入力 
 
 ORG = rgb2gray(ORG); colormap(gray); colorbar; 
 
 imagesc(ORG); axis image; % 画像の表示 
 
 pause; % 一時停止 

 
 
 % ２階調画像の生成 
 
 IMG = ORG>128; 
 
 imagesc(IMG); colormap(gray); colorbar;  axis image; 
 
 pause; 
 
 
 % ４階調画像の生成 
 
 IMG0 = ORG>64; 
 
 IMG1 = ORG>128; 
 
 IMG2 = ORG>192; 
 
 IMG = IMG0 + IMG1 + IMG2; 
 
 imagesc(IMG); colormap(gray); colorbar;  axis image; 
 
 pause;
 
  % ８階調画像の生成
  
IMG0 = ORG>32;

IMG1 = ORG>64;

IMG2 = ORG>96;


IMG3 = ORG>128;

IMG4 = ORG>160;

IMG5 = ORG>192;

IMG6 = ORG>224;

IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;

imagesc(IMG); colormap(gray); colorbar; axis image;

pause;


２．	実行結果

 ![原画像](https://github.com/enazii0312/image/blob/master/and2-1.jpg)
 
図１　原画像のグレースケール(300×300)


  ![原画像](https://github.com/enazii0312/image/blob/master/and2-2.jpg)
  
図２　2階調画像

  ![原画像](https://github.com/enazii0312/image/blob/master/and2-3.jpg)
  
図３　4階調画像

  ![原画像](https://github.com/enazii0312/image/blob/master/and2-4.jpg)
  
図４　8階調画像

３．	考察
　今回の課題は画像を2階調、4階調、8階調表示にするものであった。
2階調とは１つの閾値を境に、閾値未満なら黒、閾値以上なら白というように画像を2値化したもののであり、その結果が図２であり、図１と比較すると白と黒だけで画像が表現されているのが確認できる。
4階調の閾値は3つになる。n階調の閾値は256/nで求める事ができ、その値の倍数が閾値の基準となる。4階調の場合は256/4 = 64なので、閾値は64、64×2=128、64×3＝192となる。そしてこの閾値を用いた2階調画像(閾値64で生成、閾値128で生成、閾値192で生成の計3つ)がそれぞれ生成される。この閾値が異なる2階調画像を全て合成する事によって4階調画像が生成される。
図２と図３を比較すると図２には無い輪郭のようなものが確認できる。
　8階調の閾値は32、64、96、128、160、192、224の7つになる。4階調の時と同様に閾値毎に2階調画像が生成され、全て合成すると8階調画像になり、図４のようになる。図１、図３と比較すると図３より色の表現方法が増え、黒とグレーの区別がつくようになり原画像である図１にほぼ近い画像になった事が確認できた。

