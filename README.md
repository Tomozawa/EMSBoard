# EMSBoard
[BaseBoard ver4.0](https://github.com/tk20e/Base-Board-ver4.0-hw.git)上のBluePillにEMS信号を入力できるようにする基板です。

STM32F103C6T6Aが載っているBluePillを想定しています。これ以外の基板を使用する場合、EMSが入力されるピンが5Vトレラントであることを確認してください。

EMS信号はPA4に入力され、論理は以下の通りです。
| 状態 | ピン電圧 |
| ---- | ---- |
| 平常 | HIGH |
| 異常 | LOW |

作り方は以下の通りです。
1. R、Dが付いた部品をはんだ付けする(部品番号はBaseBoard ver4.0)と合わせてあります。
1. [2P平型のXHポスト](https://akizukidenshi.com/catalog/g/gC-12262/)をつける
1. [ピンヘッダ](https://akizukidenshi.com/catalog/g/gC-07199/)をつける(リンク先は10Pだが20Pがあるとなおよい)(足が長いタイプを購入すること)

使い方は以下の通りです。
1. BaseBoardを挿入するピンソケットにEMSBoardを挿入する。この際、EMSBoard上のXHポストがBaseBoard上のXHポストの方を向くようにする。
1. [XHハーネス(自作してもいい)](https://www.sengoku.co.jp/mod/sgk_cart/detail.php?code=EEHD-5BA7)で、BaseBoardのEmergencyボタンを付けるポストと、EMSBoardのポストを接続する(クロス配線でもストレート配線でもOK)(かならずU2に近い方のコネクタに挿す。逆にするとボタンに対して反応しない)
1. 残ったポストにはボタンを接続するか、何もつけないでおく
1. ボタンを操作するとEMSBoard上の赤色LEDが点灯したり消えたりすることを確認する

## 注意点
- BaseBoardが複数あり、すでに他のBaseBoard上に非常停止ボタンがつながっている場合、EMSBoardと接続されていない側のポストには非常停止ボタンがつけられません。
- 初期版(ver1.0)では誤ってPB10をEMS入力としていたため、初期版とそれ以降ではEMS入力ピンが異なります。
- 初期版(ver1.0)では、BaseBoard上のDIN_Fに当たるピン(PB10)をEMS入力として使用しているために、当該ピンは入出力として使えません。初期版は非推奨です。