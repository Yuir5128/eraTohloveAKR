=====================================================
●eraToLoveA02/20200323パッチ_read me●
=====================================================
バグなどあるかもしれません　ご了承ください
----------------------------------------------------
以下のファイルの適用を前提としてます

・eraToLoveA02用パッチまとめ20190410
（【刀剣乱舞】eraToloveを語るスレ 206 より）

・eraToLoveA02パッチまとめ
（【刀剣乱舞】eraToloveを語るスレ 220 より）
※eraToLoveA02パッチまとめ　は、
　eraToLoveA02南海肥前追加+α　eraToLoveA02白山追加+α　eraToLoveA02もろもろ追加　の３つのパッチと
　同一の内容のため、それらを既に導入している場合は当てなくて大丈夫です

・eraToloveA20191207パッチ
（【刀剣乱舞】eraToloveを語るスレ 222 より）

・eraToloveA20191229パッチ
（【刀剣乱舞】eraToloveを語るスレ 228 より）

・eraToloveＡ用パッチささやかパッチ
（【刀剣乱舞】eraToloveを語るスレ 233 より）

----------------------------------------------------
●導入方法
１.このパッチの各フォルダを、本体の各フォルダに上書きする
----------------------------------------------------
●パッチ内容解説
・오니마루 쿠니츠나の追加
・ユニットの追加や変更
・バグ修正など
----------------------------------------------------
バグ報告などありましたら、掲示板で呼びかけてもらうか、こちらのツイ垢にご一報ください（ＤＭ해방してます）。
@BvrP28R5CHXSaWV
----------------------------------------------------
2019.12.29　りりー(원작자)/도검난무 채널(역자)拝

=====================================================
以下　細かい内容
=====================================================
----------------------------------------------------
●キャラ追加関連
----------------------------------------------------
・以下のキャラを追加しました

오니마루 쿠니츠나			Chara21

・以下のキャラの好感度をいじりました

미카즈키 무네치카			Chara3
오오덴타 미츠요			Chara13
쥬즈마루 츠네츠구			Chara17
이치고히토후리			Chara25
오오카네히라				Chara53
히게키리				Chara107

素質や好感度は主観なので、好みでいじってください

※通常衣装で、腰に巻いている上着は無視しています

※内番衣装のジャージの下に何を着ているのかわからなかったので、とりあえずＴシャツに設定しています

※角は머리카락飾りとして処理

【追加ファイル】
Chara21.csv

【修正ファイル】
Chara3.csv　Chara13.csv　Chara17.csv　Chara25.csv　Chara53.csv　Chara107.csv
Item.csv　_Rename.csv
CHARA_MANUAL.ERB　CHARA_PRICE.ERB　CLOTHES2.ERB　NATION_NAME.ERB　PANCTION.ERB
PANT_SET.ERB　DAILY_LIFE_COMMON.ERB　CONCERT.ERB

----------------------------------------------------
●ユニット関連
----------------------------------------------------
○ユニット名を判定する関数内で使われていた変数LOCALを変更
	とりあえず200まで枠とってます

○ユニット名の優先度を加味してユニット名の分岐追加

○ユニットの追加・変更
	발利宝剣→발利宝剣・발利組に変更
		三日月と骨喰の２振ユニットならば발利宝剣になります
		該当刀数も大幅に追加
	前田家・特命調査組・鬼切コンビetcを追加
	大阪城組に白山を追加

----------------------------------------------------
●バグ修正　他
----------------------------------------------------
○Talent.csv
	억압と저항の項目について修正
		억압は욕망LVで、저항は순종LVで消滅する

○HELP1.ERB
	절륜の項目の関数名？を修正
	조루・지루の項目を追加

○PANT_SET.ERB
	自身で設定した汎用喘ぎを削除できるようにしました
	デフォルトで設定されている汎用喘ぎを参照できるようにしました

○EVENT_M_COM.ERB　9279行目～
	「PALAM:13」となっていた部分を「PALAM:6」に修正
		COM361_촉수유선고문.ERBを参考にしました

○WORK.ERB　@CHARA_SELL
	정액중독を見るはずが자위중독を見ていた点
	게이끼を見るはずが욕망を見ていた点
	레즈끼を見るはずが자위중독を見ていた点　の３つについて修正
		コメントに合わせました

○EVENT_T.ERB　232行目～
	助손がいない場合の分岐を書き忘れていたのを修正
		スレでの指摘　ありがとうございました

○PRINT_CHARA_LIST.ERB　CHARA_SELLING_PRICE(ARG)
	売却額に関して素質남자にマイナス補正がかかっていたのを修正
		あくまで表示上だったので、プレイに支障はないはずです
	難易度方のマイナス補正はそのまま

○TRACHECK.ERB　3030行目～
	「B둔감」となっていた部分を「B민감」に修正
		コメントに合わせました

----------------------------------------------------
●資料フォルダ
----------------------------------------------------
・フラグ表の修正
	経験の項目で抜けていた分を追加

・ユニット表に追加ユニット諸々を追記

=====================================================
直すか迷って直していない部分　直せなかった部分
（以前からの分も引き続き載せています）
=====================================================
----------------------------------------------------
●커닐링구스がSOURCE:쾌Cと処理されている点
----------------------------------------------------
※仕様なのかバグなのか判別がつかないので直してません

커닐링구스は、コマンドの分類ではＶ系に分類されているが（参照：Train.csv　他）
実際にされている処理はSOURCR:쾌Cのみ（COMF40_커닐링구스.ERB）

※PANTVOICE.ERB　287行目ではＣ系に分類されている

※改変元（erahetaA私家版）や他バリアントでは、Ｃ系に分類

----------------------------------------------------
●처녀・동정・백버진を奪った相손　の表示が
実際に奪った相손と異なる場合がある
----------------------------------------------------
※仕様なのかバグなのか判別がつかないので直してません

처녀・동정・백버진を奪った相손は
奪われたキャラのCSTR:10（처녀）　CSTR:11（동정）　CSTR:12（백버진）に記録されています
（TRACHECK.ERB　に該当処理部分）

しかし、以下のような状況だと実際に奪った相손と異なった相손が記録されることがあるようです
例）調教において、調教者が助손に交代している状況で
調教者（助손）が挿入コマンドによって奴隷の처녀・동정・백버진を奪った場合
記録される名前がマスターの名前になる

マスターが助손に命令して奴隷の처녀・동정・백버진を奪わせた、と考えられなくもないため
仕様なのか、バグなのかの判別がつかず直していません

※へたくしょんの面識フラグは、上記の例では奴隷の처녀・동정・백버진を奪った相손として
助손を記録している

※マスターが調教者のまま、助손삽입명령コマンドによって奴隷の처녀・동정・백버진を奪った場合
記録される名前は助손の名前

----------------------------------------------------
●「장갑」と「マント（死装束）」が同時に着用できない
----------------------------------------------------
※両方TEQUIP:0[특수1]に含まれるので仕様的に当然
※解決方法が思いつかないので直してません

初期設定の着衣に「장갑」と「マント（死装束）」の両方を含むキャラの場合
今のところ「장갑」しか反映されてません

----------------------------------------------------
●初期設定の着衣に「타이츠」がある男士の「타이츠」の着脱
----------------------------------------------------
※타이츠が、アイテムの타이츠（ITEM:37）として扱われてるだけなので仕様的に当然
※解決方法が思いつかないので直してません

該当男士（内番着の秋田　清麿）の着衣設定には「타이츠」が反映されてます
しかし、着衣画面に「타이츠」の項目がないので
「ひんむく」を選択する、もしくは直接番号（56）を打つ方法でしか脱がせられません
そして、再度着用できません
（「外出着の着用」を選択すると、初期着衣の設定が内番着でも通常衣装を着る）

----------------------------------------------------

