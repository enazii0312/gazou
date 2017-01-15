# 課題５
画像処理工学

判別分析法を用いて画像二値化せよ．

１．	使用プログラム


filename = uigetfile('*');

ORG=imread(filename); % 原画像の入力

ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

imagesc(ORG); colormap(gray); colorbar;

pause;



H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納

myu_T = mean(H);

max_val = 0;

max_thres = 1;

for i=1:255

C1 = H(1:i); %ヒストグラムを2つのクラスに分ける

C2 = H(i+1:256);

n1 = sum(C1); %画素数の算出

n2 = sum(C2);

myu1 = mean(C1); %平均値の算出

myu2 = mean(C2);

sigma1 = var(C1); %分散の算出

sigma2 = var(C2);

sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出

sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出


if max_val<sigma_B/sigma_w

max_val = sigma_B/sigma_w;

max_thres =i;

end;

end;



IMG = ORG > max_thres;

imagesc(IMG); colormap(gray); colorbar;

pause;





２．	実行結果

 ![原画像](https://github.com/enazii0312/image/blob/master/753.JPG)
 
図１　原画像(1280×1280)

 ![原画像](https://github.com/enazii0312/image/blob/master/7535-1.jpg)
 
図２　原画像のグレースケール(1280×1280)

 ![原画像](https://github.com/enazii0312/image/blob/master/7535-2.jpg)
 
図３　判別分析法を用いた図２の二値化画像
３．	考察
　今回の課題は判別分析法を用いて画像を二値化画像にするものであった。
判別分析法とは対象物の濃度と背景の濃度とがそれぞれ最もよくまとまり、かつ対象物と背景の違いが際立つように閾値を定める方法である。具体的な手順を以下に示す。
①	全画素の濃度の平均値をµ_Tとする。
②	濃度tで分けた時のクラスiの分散をσ^2_i、平均値をµ_i、画素数をn_iとする。
③	クラス内分散　σ^2_w=(n_1σ^2_1+n_2σ^2_2)/(n_1+n_2)を求める。
④	クラス間分散　σ^2_B={n_1(µ_1-µ_T)^2+n_2(µ_2-µ_T)^2}/(n_1+n_2)を求める。
⑤	σ^2_B/σ^2_wを最大とするようにtを定める。

この方法を用いて二値化画像にした結果が図３である。背景の木も対象物として捉えられているが、図１、図２と比較すると画像の構図がそのまま二値化されてシルエット化している事が確認できた。
