# EMSBoard
[BaseBoard ver4.0](https://github.com/tk20e/Base-Board-ver4.0-hw.git)上のBluePillにEMS信号を入力できるようにする基板です。

STM32F103C6T6Aが載っているBluePillを想定しています。これ以外の基板を使用する場合、EMSが入力されるピンが5Vトレラントであることを確認してください。

EMS信号はPB10に入力され、論理は以下の通りです。
| 状態 | ピン電圧 |
| ---- | ---- |
| 平常 | HIGH |
| 異常 | LOW |

使い方は以下の通りです。
1. R、Dが付いた部品をはんだ付けする(部品番号はBaseBoard ver4.0)と合わせてあります。
1. 2P平型のXHポストをつける
