# まず、ロギングとは何か？


## お話し１

田中さんは、 📁 `baseball-watching` フォルダーの中に有る、自分の作った 📄 `baseball-watching.exe` ファイルを朝１０時にダブルクリックした。  
画面には背景一面が黒いウィンドウが出て、白い文字が下から上へ忙しくスクロールしている。  
とりあえず、１か月ぐらい放置しようと、ＰＣの電源を付けたまま寝た。  

次の日の朝、ＰＣ画面を見ると、昨日画面に出していた背景一面が黒いウィンドウが消えていた。  
田中さんは、昨日出しっぱなしにしていたそのウィンドウがなぜ消えているのか知りたいと思った。  
📁 `baseball-watching/logs` フォルダーの中の 📄 `error.log` ファイルを開いた。  


📄 `baseball-watching/logs/error.log` > 最終行:

```plaintext
[2025-11-23 15:34 +09] baseball-watching/src/main.go 176: open "baseball-watching/assets/data/score-book-1950-03.json" file, but it not found.
```

👆 📄 `error.log` ファイルを開くと、

意訳：  

> 日本時間２０２５年１１月２３日　１５時３４分に  
> プログラムの 📄 `baseball-watching/src/main.go` ファイルの 176 行目に書いてある、  
> 📄 `baseball-watching/assets/data/score-book-1950-03.json` ファイルを開くというコードを実行しようとしたが、
> そのような名前のファイルは見つからなかった。  

というメッセージを最後に途切れていた。  

田中さんはとりあえず 📁 `baseball-watching/assets/data/` フォルダーを開けて中を見ることにした。  
📄 `baseball-watching/assets/data/score-book-1950-03.json` というファイルは無かった。  


## お話し１　解説

📄 `baseball-watching/logs/error.log` ファイルが無かったら、以下のことが分からないままになっているところだった。  

* そのプログラムは、日本時間２０２５年１１月２３日　１５時３４分より前まで正しく仕事しており、それより後ろでは仕事してない。
* 📄 `baseball-watching/assets/data/score-book-1950-03.json` というファイルが無いこと。
* プログラムの 📄 `baseball-watching/src/main.go` ファイルの 176 行目より前で、田中さんはこの不具合に対して何か対応するコードを書く必要があるかもしれないこと。

🫘 豆知識：  

* 📄 `baseball-watching/logs/error.log` のようなファイルを、 **ログ・ファイル** と呼びます。 
