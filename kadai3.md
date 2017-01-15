# 課題３
画像処理工学


１．	使用プログラム

 clear; % 変数のオールクリア 
 
 
 filename = uigetfile('*')
 
 ORG=imread(filename); % 原画像の入力  
 
 ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換 
 
 
 imagesc(ORG); colormap(gray); colorbar; % 画像の表示 
 
 pause; 
 
 
 IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換 
 
 imagesc(IMG); colormap(gray); colorbar; 
 
 pause; 
 
 
 IMG = ORG > 96; 
 
 imagesc(IMG); colormap(gray); colorbar; 
 
 pause; 
 
 
 IMG = ORG > 128; 
 
 imagesc(IMG); colormap(gray); colorbar; 
 
 pause; 
 
 
 IMG = ORG > 192; 

imagesc(IMG); colormap(gray); colorbar;



 
２．	実行結果

 ![原画像](https://github.com/enazii0312/image/blob/master/and3-1.jpg)
 
図１　原画像のグレースケール(300×300)


  ![原画像](https://github.com/enazii0312/image/blob/master/and3-2.jpg)
  
図２　輝度値64を閾値にした画像

  ![原画像](https://github.com/enazii0312/image/blob/master/and3-3.jpg)
  
図３　輝度値96を閾値にした画像

  ![原画像](https://github.com/enazii0312/image/blob/master/and3-4.jpg)
  
図４　輝度値128を閾値にした画像

  ![原画像](https://github.com/enazii0312/image/blob/master/and3-5.jpg)
  
図５　輝度値192を閾値にした画像
 

３．	考察
　今回の課題は輝度値を閾値として扱い、閾値未満なら黒、閾値以上なら白という二値化画像を生成するものであった。図１の原画像では確認できる消しゴムケースの折り目の立体感が閾値を上げていくにつれて確認できなくなっていくことが図２～図５でわかる。また、消しゴムケースの文字が図２ではぼやけて読みにくいが図４では図１とほぼ変わらないくらいはっきりとしている。図５の様に閾値を上げすぎてしまうと逆に読みにくくなってしまうのも確認できる。この結果より、閾値を適切に設定することで画像をより鮮明にすることができるという事がわかった。
