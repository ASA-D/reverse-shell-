# reverse-shell-

システムを乗っ取る方法はたくさんある。
一般的な方法は、対話型シェルを利用することで、オペレーティングシステムの完全な制御を試みることが可能だ。
しかし、ほとんどの標準的なファイアウォールは、遠隔地からの直接接続をブロックしている。
これを回避する方法の一つとして、リバースシェルを使用する方法がある。
リバースシェルとは、ローカルのcmd.exe（Windows用）やbash/zsh（Unix系用）のコマンドを実行し、その出力をターゲット端末に送るプログラムであり、ターゲットマシンが攻撃者マシンへの接続を行い、攻撃者マシンは指定されたポートで接続をリッスンする。
これから実装するコードの基本的な考え方は、攻撃者のマシンが接続をリッスンし続けるというものである。
クライアント（またはターゲットマシン）が接続すると、サーバーはターゲットマシンにシェルコマンドを送信し、ハッキングする。



 1. リバースシェルの基礎知識
 
 1-1.クライアントとサーバー
 
 サーバーと言われているが、実際にはただのパソコンである。このサーバーは外部のクライアントからの接続に対し、ある特定の情報を送るものである。
