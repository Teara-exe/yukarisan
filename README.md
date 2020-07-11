# yukari-san

プリンセスコネクト Re:Diveにおけるクランバトルを円滑に進行する支援ツールです。  
DiscordのBotとして利用します。

- 凸報告をしてもらい、残り人数の把握をする
- 残り凸数から大体の周回数を計算する
- オマケ機能　(ガチャ、スコア→周回数計算)

## 使用方法

凸報告のテキストチャンネルに"凸"と書き込みます。  
botがスタンプを付けるので、結果に応じて対応するスタンプを押します。  


## 一般コマンド

- 凸/a  
攻撃宣言、詳しくは別画像参照

- タスキル/taskkill  
タスクキルをメモする  
以後、！のスタンプが追加される  
タスキルを取り消す場合は、タスキルのメッセージを削除する  
(新しく"タスキル"と入力して、そのメッセージを消しても良い)  
タスキル状態は朝5時にリセットされる  

- メモ/memo  
「メモ 夜に殴ります」のように入力すると、持ち越し欄にメモが追加される  
表示例)  
持ち越し 1人  
いずみ ジャッカルシーフ:40秒 夜に殴ります  

- 通知/notice  
「通知 5」のように入力すると、5ボスが来たときに@で教えてくれる  
凸完了した時、通知はリセットされる(もしくは「通知 0」と入力)  
「通知」だけで今の通知状況をスタンプで教えてくれる  

- nextboss/prevboss  
nextbossでボスを進めて、prevbossでボスを戻す  
誰かが報告を間違えた時など、ボスが違うときに使用する  

- history  
「history 名前」でその人の凸履歴が表示される

- ガチャ/gacha  
ガチャをおこなう

- score  
「score 数値(万)」でそのスコアが何周目のどの敵に該当するかを表示する  
数値は万単位(下4桁を削る)

- gdata  
現在のガチャ確率を表示する

- gacha10000  
10000回ガチャを行う(ガチャデータ検証用)

- gachalist  
ガチャスケジュールの表示

## 全体セッティングコマンド

このコマンドはすべてのギルドに影響するコマンドです  
crandata/ 以下のファイルから自分のサーバを探し、admin=Trueとしたサーバのみ実行できます  
基本的には、最新のsetting.jsonをGithubからダウンロードすれば使うことはありません  

- gachaadd  
ガチャデータを追加する  
usage)gachaadd[gachatype][startdate][name]  
gachatype  以下の1文字を入れる  
-- 1,2,3 恒久的に出現するレアリティ  
-- f プリフェス限定  
-- l 限定(追加されない)  
-- d 2倍(星3が2倍、ピックアップが1.4%)  
-- p プライズガチャ  
startdate  ガチャが始まる期間  
name  ガチャに追加されるキャラ(,で区切って複数可能)  
ex)gachaaddl2020/07/10 12:00:00マコト(サマー),マホ(サマー)  

- gachadelete  
gachaaddで追加したキャラの削除  
usage)gachadelete[index]  
index  gachalist のindexを入力  
ex)gachadelete1  

- term  
クランバトルの期間を設定する  
usage)term[start m/d],[end m/d]  
ex)term06/25,06/29  

- bossname  
usage)term[boss1],[boss2],[boss3],[boss4],[boss5]  
クランバトルのボスの名前を設定する  

## 導入方法

discord.pyやDiscordにおけるBotの導入方法は省略します。  

discordbot.pyを置いたディレクトリにtokenkeycode.pyというファイルを作成します。  
内容は以下の通りで、discordのトークンを記入します。

#--ここから--  
TOKEN = 'xxxxxxxxxxxxxxxxxxxxxxxx.yyyyyy.zzzzzzzzzzzzzzzzzzzzzzzzzzz'  
#--ここまで--  

「凸報告」「状況報告」の名前でテキストチャンネルを作ります。  
「凸報告」は全員が書き込める状態、  
「状況報告」はユカリさんBot以外書き込めない状態が良いでしょう。  

名前を変えたい場合は、discord.pyのinputchannel, outputchannel を変更して下さい  


