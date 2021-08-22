# Armors キーパッド ビルドガイド
- [キット内容](#キット内容)
- [組み立て方（はんだ付け）](#組み立て方はんだ付け)
- [動作テスト](#動作テスト)
- [組み立て方（後半）](#組み立て方後半)
- [カスタマイズ](#キーマップの確認変更方法)
- [おまけ](#おまけ)

## キット内容
![パーツ一覧](img/parts2.jpg)  
||部品名|数| |
|-|-|-|-|
|1|メインボード（黒・大）|1||
|2|ミドルプレート（透明・中）|1||
|3|ボトムプレート（黒・中）|1||
|4|ボトムプレート（透明・小）|1||
|5|ネジ（短）|12|3mm|
|6|ネジ（長）|8|5mm|
|7|スペーサー（短）|6|3mm|
|8|スペーサー（長）|4|8mm|
|9|ダイオード|17||
|10|リセットスイッチ|1||
|11|ゴム足|4||

## キット以外に必要なもの
|部品名|数|||
|-|-|-|-|
|Pro Micro コンスルー付き|1||[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/promicro-spring-pinheader)|
|キースイッチ|17|Kailh Choc V1 もしくは V2||
|キーキャップ|17|スイッチに対応したもの・1U||
|Micro USB ケーブル|1|データ通信対応でUSB2.0 Micro-Bのもの。|

## オプション
|部品名|数|||
|-|-|-|-|
|SK6812MINI-E|17|光らせる場合。[取り付け方](led.md)|[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/sk6812mini-e-10)|
|WS2812B|3|無くてもバックライトだけ光ります。|[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/a0800ws-01-10)|
|表面実装タイプのダイオード|17||[遊舎工房様販売ページ](https://shop.yushakobo.jp/products/a0800di-02-100)|
|両面テープ||ねじの頭の0.5㎜より厚いものがおすすめです。||
 
## 必要な工具
|工具名| |
|-|-|
|はんだごて||
|はんだごて置き場||
|鉛入りはんだ||
|細いドライバー|+の1番ドライバー。|
|ニッパー等ダイオードの足を切れるもの|金属用でない場合刃こぼれします。|
|Microsoft Edge、もしくはGoogle Chrome||

## あると便利な工具
|工具名||
|-|-|
|耐熱シリコンマット||
|斜めに切ったタイプのこて先||
|温度調節可能なはんだごて|300度-350度前後|
|ピンセット|LEDには必須|
|フラックス|LEDには必須|
|テスター||
|フラックスリムーバー||
|マスキングテープ||
|はんだ吸い取り線||

## 組み立て方（はんだ付け）
正しくはんだ付けが終わるとこのようになります。
![](img/full2.jpg)  

はんだ付けのやり方は動画で見るとわかりやすいです。  
パーツは思ったより壊れないので落ち着いて作業すると失敗しにくいです。  
 - ホームセンターのDCMさんの解説動画(58秒～) https://www.youtube.com/watch?v=JFQg_ObITYE&t=58s
  
それではダイオードをD1からD17まで取り付けます。  
足を曲げて裏から差し込みます。  
![](img/diode1.jpg)  
ダイオードには向きがあります。三角形の先の棒と黒線を合わせましょう。  
表で更に足を曲げて抜けないようにします。  
![](img/diode2.jpg)  
ダイオードと並行に曲げるとあとでキースイッチに干渉しにくいです。
はんだ付けをして足を切ります。  
![](img/diode3.jpg)  
  
リセットスイッチを裏から差し込み表ではんだ付けします。  
![](img/reset1.jpg)  
フラックスクリーナーを使う場合はここで表面をきれいにしましょう。
![](img/reset2.jpg)  
  
キースイッチを表から差し込み裏ではんだ付けします。  
![](img/keyswitch.jpg)  
  
メインボードの裏にコンスルーを挿します。  
コンスルーの窓が高くて両方とも同じ向きになるように設置します。  
![](img/promicro1.jpg)   
挿すだけではんだ付けはしません。  
コンスルーにPro Microを挿します。TX0, RAW, USBの位置をシルク印刷と合わせましょう。  
![](img/promicro2.jpg)   
そして、Pro Micro側のコンスルーの足を半田付けします。  
![](img/promicro3.jpg)   

## 動作テスト
Pro Microに動作ソフト（ファームウェア）を書き込んで動作確認をしましょう。  
キットとPCをUSBケーブルでつないでください。   

ファームウェアをダウンロードしてPro Micro Web Updaterにアクセスしてください。
- テスト用ファームウェア [armors_test.hex](https://github.com/Taro-Hayashi/Armors/releases/download/1.0/armors_test.hex)
- Pro Micro Web Updater https://sekigon-gonnoc.github.io/promicro-web-updater/index.html

ファイルの選択ボタンを押してダウンロードしたファームウェアを指定したら、flashボタンを押しましょう。  
![](img/promicrowebupdater1.jpg)  

ブラウザのアドレスバーからメッセージが出てきたら、キットのリセットスイッチを押します。      
すると選択欄にArduino Microが出てきてクリックできるようになります。  
![](img/promicrowebupdater2.jpg)  

選択して接続を押すと書き込みが終わります。  
![](img/promicrowebupdater3.jpg)  
ファームウェアを更新する時もこの手順で行います。    

タイプすると1-17の数字が打てるはずです。   

お疲れ様でした。問題がなければはんだ付けは終了です。

## 組み立て方（後半）
USBケーブルを抜いてプレートを組付けます。  
アクリルからは保護フィルムを剥がしてください。割れやすいので気をつけましょう。  
  
メインボード裏面の赤丸の箇所にスペーサー（短）をネジ（短）で取り付けてミドルプレート（透明・中）を嵌めます。
![](img/bottom4.jpg)  
ボトムプレート（黒・中）をネジ（短）で止めます。  
  
メインボードの残ったネジ穴にスペーサー（長）をネジ（長）で取り付け、ボトムプレート（透明・小）をネジ（長）で止めます。  
![](img/bottom5.jpg)   

キーキャップを取り付けたら本番用のファームウェアに更新しましょう。
- [armors_via.hex](https://github.com/Taro-Hayashi/Armors/releases/download/1.0/armors_via.hex)

ゴム足を貼ったら完成です。  
![](img/rubber.jpeg)  
![](img/done.jpeg)  

## キーマップの確認、変更方法
このキットはレイヤー機能を使っています。
![](img/layout.png)
[Keyboard Layout Editor で見る](http://www.keyboard-layout-editor.com/##@_name=Layout%20-%20Armors%20KEYPAD;&@_x:0.5&a:7;&=F1&=F2&=F3&=F4&=F5&_x:1.5;&=F1&=F2&=F3&=F4&=F5&_x:1.5&c=#e0cb58&fa@:1;;&=前のパターン&_c=#cccccc;&=&=&_c=#e0cb58;&=次のパターン&_c=#decf7e;&=;&@_c=#cccccc&a:5&f:3;&=!%0A%0A%0A%0A%0A%0A1&_f:3;&=/@%0A%0A%0A%0A%0A%0A2&_f:3;&=#%0A%0A%0A%0A%0A%0A3&_f:3;&=$%0A%0A%0A%0A%0A%0A4&_f:3;&=%25%0A%0A%0A%0A%0A%0A5&_fa@:0&:1&:0&:0&:0&:0&:1;;&=~%0A長押しLOWER%0A%0A%0A%0A%0A%60&_x:0.5&c=#8792d6&a:7;&=F6&=F7&=F8&=F9&=F10&_c=#98a3d4;&=&_x:0.5&c=#cccccc;&=&_c=#e0cb58;&=色相+&=彩度+&=明度+&_fa@:1;;&=スピード+&_c=#cccccc;&=;&@_a:5&f:3;&=%5E%0A%0A%0A%0A%0A%0A6&_f:3;&=/&%0A%0A%0A%0A%0A%0A7&_f:3;&=*%0A%0A%0A%0A%0A%0A8&_f:3;&=(%0A%0A%0A%0A%0A%0A9&_f:3;&=)%0A%0A%0A%0A%0A%0A0&_c=#aaaaaa&a:7&f:3;&=shift&_x:0.5&c=#8792d6&f:3;&=F11&_f:3;&=F12&_c=#cccccc;&=&=&=&_c=#aaaaaa;&=&_x:0.5&c=#e0cb58&f:3;&=ON//OFF&_f:3;&=色相-&_f:3;&=彩度-&_f:3;&=明度-&_f:3;&=スピード-&_c=#aaaaaa;&=)  

使わないキーを削除したり使用頻度の高いキーを押しやすい位置に変更してみましょう。  
  
ChromeかEdgeでRemapにアクセスしてください。  
- Remap https://remap-keys.app/
  
![](img/remap1.png)  
左を選んで進んでいくとアドレスバーからメッセージが出てキーボードを選択できます。  
  
キーマップをドラッグアンドドロップで変更し右上のflashボタンを押すと反映されます。
![](img/remap3.png)  
  
## 液晶タブレットに乗せる場合
1番上の行を引っ掛ける事で液タブに乗せる事ができます。
![](img/tab.jpeg)　　
ゴム足を外して両面テープで固定すると安定します。  
跡が残るといけないので画面には保護フィルムを貼ってください。  

## おまけ
寸法です。ダンボールで作れるペーパークラフトもあります。
![](img/size.png)　　
![](img/danbo.jpg)　　
- [realsizeA4.pdf](https://github.com/Taro-Hayashi/Armors/releases/download/1.0/realsizeA4.pdf)  
- ネットプリント番号: SD9TTJJF 8/12まで　

A4サイズです。定規があればプリントしなくても作れます。

ファームウェアのフォルダ  
https://github.com/Taro-Hayashi/qmk_firmware/tree/master/keyboards/armors  
  
VIA用JSONファイル [armors.json](https://github.com/Taro-Hayashi/Armors/releases/download/1.0/armors.json)  
  
ミドル、ボトムプレートのデザインデータ  
[armors_plates.zip](https://github.com/Taro-Hayashi/Armors/releases/download/1.0/armors_plates.zip)  
発注先のルールに沿ってデータを修正してください。  
  
ご不明な点があればBOOTHのメッセージかtwitterのリプライでいつでも聞いてください。  
販売ページ: https://tarohayashi.booth.pm/items/3154455
  
foostan様のフットプリントを流用、改変して使わせていただきました。  
https://github.com/foostan/kbd/  
https://github.com/foostan/kbd/blob/master/LICENSE  
