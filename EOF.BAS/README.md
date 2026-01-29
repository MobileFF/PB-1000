#### PB-1000でUARTのEOF(&H1A)を出力するBASICプログラム

カシオ PB-1000のメニュー機能のUART(RS232C)出力([save])は、最後にEOF(&H1A)を出力しない仕様になっているため、そのままでは受信側で通信終了を検出できないことがあります。

そのため、PB-1000側に以下のようなBASICプログラムを用意しておき、[save]終了後にこのプログラムを実行すると便利です。

```basic
1 'EOF.BAS
1000 OPEN"COM0:7,N,8,1,N,N,N,N,N" FOR OUTPUT AS #1
1010 PRINT#1,CHR$(&H1A)
1020 CLOSE #1
```
  
以上
