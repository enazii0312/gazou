# 課題１
画像処理工学

課題１　標本化間隔と空間解像度　　　　13ec092 星　遥介
　画像をダウンサンプリングして（標本化間隔を大きくして） 表示せよ．

１．	使用プログラム

clear; % 変数のオールクリア 
 
 filename = uigetfile('*') 　%原画像の入力
 ORG=imread(filename); 　% 原画像の入力 
imagesc(ORG); axis image;　 % 画像の表示
xlabel('x');ylabel('y');　%x軸とy軸の表示
pause; 　% 一時停止 
 
  IMG = imresize(ORG,0.5);　 % 画像の縮小 
 IMG2 = imresize(IMG,2,'box');　 % 画像の拡大 
 imagesc(IMG2); axis image; 　% 画像の表示 
xlabel('x');ylabel('y');　% x軸とy軸の表示
 pause; 　% 一時停止 
 
 
 IMG = imresize(IMG,0.5);　 % 画像の縮小 
 IMG2 = imresize(IMG,4,'box');　 % 画像の拡大 
 imagesc(IMG2); axis image;　 % 画像の表示 
 xlabel('x');ylabel('y');　% x軸とy軸の表示
 pause;　 % 一時停止 
 
 
 IMG = imresize(IMG,0.5);　 % 画像の縮小 
 IMG2 = imresize(IMG,8,'box');　 % 画像の拡大 
 imagesc(IMG2); axis image; 　% 画像の表示 
 xlabel('x');ylabel('y');　 %x軸とy軸の表示
 pause;　 % 一時停止  
 
 IMG = imresize(IMG,0.5); 　% 画像の縮小 
 IMG2 = imresize(IMG,16,'box');　 % 画像の拡大 
 imagesc(IMG2); axis image; 　% 画像の表示 
 xlabel('x');ylabel('y');　 %x軸とy軸の表示
 pause;　 % 一時停止 
 
 
 IMG = imresize(IMG,0.5);　 % 画像の縮小 
 IMG2 = imresize(IMG,32,'box');　 % 画像の拡大 
 imagesc(IMG2); axis image;　%画像の表示
 xlabel('x');ylabel('y');　% x軸とy軸の表示


２．	実験結果
使用画像
 
[図1　and.png(170×170)](https://github.com/enazii0312/image/blob/master/and.png)
 図1　and.png(170×170)

実行結果
 
　![図2　実行１回目(1/2サンプリング)](https://github.com/enazii0312/image/blob/master/and1-1.jpg)
 図2　実行１回目(1/2サンプリング)
 
![図3　実行2回目(1/4サンプリング)](https://github.com/enazii0312/image/blob/master/and1-2.jpg)
図3　実行2回目(1/4サンプリング)

 
![図4　実行3回目(1/16サンプリング)](https://github.com/enazii0312/image/blob/master/and1-3.jpg)
図4　実行3回目(1/16サンプリング)
 
![図5　実行4回目(1/32サンプリング)](https://github.com/enazii0312/image/blob/master/and1-4.jpg)
図5　実行4回目(1/32サンプリング)

以上の結果より元の画像がサンプリングされるとぼやけるのが確認できた。また、標本化間隔を大きくするにしたがって画像のぼやけ具合が強くなることも確認できた。

３．	考察
　今回の課題は画像をダウンサンプリングしたものを表示する課題であった。ダウンサンプリングは原画像を縮小した後に原画像と同じ画像サイズで表示することで実現できる。1/2ダウンサンプリングを行った結果が図２である。これは原画像(170×170)を1/2に縮小して150×150にしたものを2倍に拡大し、原画像(170×170)と同じ画像サイズで表示させたものである。図３は原画像を1/4に縮小にしたものを4倍に拡大、図４は1/8に縮小にしたものを8倍・・・と同様の方法で図２～図６のような結果を表示する事が出来た。図２～図６より画像をダウンサンプリングすると原画像より情報量が少ないのでぼやけた結果になる事が確認できた。また、間隔が大きくなるほど情報量が少なくなりぼやけが強くなることも確認できた。

