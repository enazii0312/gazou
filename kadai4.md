# 課題４
画像処理工学

画素の濃度ヒストグラムを生成せよ．

１．	使用プログラム

clear; % 変数のオールクリア


filename = uigetfile('*');

ORG=imread(filename); % 原画像の入力

ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

imagesc(ORG); colormap(gray); colorbar;

pause;


imhist(ORG); % ヒストグラムの表示


２．	実行結果

 ![原画像](https://github.com/enazii0312/image/blob/master/and.png)
 
図１　原画像(170×170)

  ![原画像](https://github.com/enazii0312/image/blob/master/kadai4-1.jpg)
  
図２　原画像のグレースケール(170×170)


  ![原画像](https://github.com/enazii0312/image/blob/master/kadai4-2.jpg)
  
図３　原画像の濃度ヒストグラム

３．	考察
　今回の課題は画像の濃度ヒストグラムを生成し、確認するものであった。図２の原画像のグレースケールを濃度ヒストグラムで表示した結果が図３である。横軸が濃度で、縦軸がその濃度画素の多さで表示されている。原画像の大半は背景や緑と赤で占められているので濃度75,
 160あたりから山ができている事が確認できる。よって濃度ヒストグラムが正しく動作していることが確認できた。
 
