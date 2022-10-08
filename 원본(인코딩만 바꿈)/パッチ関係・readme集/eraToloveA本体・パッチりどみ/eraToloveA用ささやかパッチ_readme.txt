eraToloveA用ささやかパッチ

■導入方法■
eraToLoveA02用パッチまとめ20190410
eraToLoveA02まとめ20191104
eraToloveA20191207パッチ
eraToloveA20191229パッチ
以上を適用したeraToLoveA02本体（以下本体）を用意してください
当パッチの各フォルダを本体内の各フォルダに上書きしてください

────

パッチ内容

バグ修正
難易度の表記を一部変更
所持金、円、$、小判を甲州金/朱に統一

────

以下変更点

CSV\Talent.csv(28,29行目
21,無関心,:ABL:奉仕精神が上げにくい。PALAM:恭順、欲情、屈服、恐怖、反感が上がりにくい
22,感情乏しい,:ABL:奉仕精神が上げにくい。PALAMが全体的に上がりにくい
↓
21,無関心,;ABL:奉仕精神が上げにくい。PALAM:恭順、欲情、屈服、恐怖、反感が上がりにくい
22,感情乏しい,;ABL:奉仕精神が上げにくい。PALAMが全体的に上がりにくい
※本来;でコメントアウトするべき部分が:になっていたのを修正

ERB\SYSTEM.ERB(23行目
SAVESTR:0 = /240/241/242/
↓
SAVESTR:0 = /390/391/392/
※コマンド番号の変更にあわせて修正

ERB\INFO.ERB(48行目
		PRINT 普通
↓
		PRINT 普

ERB\INFO.ERB(481行目
	PUTFORM 優 
↓
	PUTFORM 易 

ERB\INFO.ERB(483行目
	PUTFORM 普通 
↓
	PUTFORM 普 

CSV\_Replace.csv(8行目
お金の単位 , 円
↓
お金の単位 , 朱

CSV\Str.csv(89行目
572,「あなたが、それらを元手に、期日までに100万円を準備する」
↓
572,「あなたが、それらを元手に、期日までに甲州金100万朱を準備する」

ERB\DEBUGMENU.ERB(82行目
PRINTL [34] - 所持金を変更する
↓
PRINTL [34] - 所持甲州金を変更する

ERB\DEBUGMENU.ERB(1281行目
PRINTFORML 現在の所持金${MONEY}
↓
PRINTFORML 現在の所持甲州金{MONEY}朱

ERB\DEBUGMENU.ERB(1295行目
PRINTFORMW 所持金を${MONEY}に変更しました
↓
PRINTFORMW 所持甲州金を{MONEY}朱に変更しました

ERB\ENDING.ERB(82行目
		PRINTFORMW 最終的には、「100日」以内に「100万円」を稼ぐことが目的です。
↓
		PRINTFORMW 最終的には、「100日」以内に「100万朱」を稼ぐことが目的です。

ERB\ENDING.ERB(90,91行目
	PRINTFORMW その期間を過ぎると、奴隷の維持費等で、毎朝所持金が減っていきます。
	PRINTFORMW 所持金が底を尽きるとゲームオーバーになりますので、
↓
	PRINTFORMW その期間を過ぎると、奴隷の維持費等で、毎朝所持甲州金が減っていきます。
	PRINTFORMW 所持甲州金が底を尽きるとゲームオーバーになりますので、

ERB\EVENT_S.ERB(104行目
	PRINTFORML 奴隷と道具の維持費、生活費に${A}かかった……
↓
	PRINTFORML 奴隷と道具の維持費、生活費に{A}朱かかった……

ERB\INFO.ERB(39,40行目
;所持小判　
PRINTFORM 所持小判：{MONEY}　
↓
;所持甲州金
PRINTFORM 所持甲州金：{MONEY}朱　

ERB\ITEM.ERB(324行目
	LOCALS = [{LOCAL,2}] %ITEMNAME:LOCAL%(%MONEY_FORM(ITEMPRICE:LOCAL)%円)
↓
	LOCALS = [{LOCAL,2}] %ITEMNAME:LOCAL%(%MONEY_FORM(ITEMPRICE:LOCAL)%朱)

ERB\ITEM.ERB(1102行目
PRINTFORML 所持金：{MONEY}円
↓
PRINTFORML 所持甲州金：{MONEY}朱

ERB\SHOP.ERB(80行目
	PRINTFORML 　(所持小判{MONEY})
↓
	PRINTFORML 　(所持甲州金{MONEY}朱)

ERB\SHOP.ERB(138行目
		PRINTFORML 目標：100日以内に$1000000稼ぎ、[納金]せよ
↓
		PRINTFORML 目標：100日以内に甲州金1000000朱稼ぎ、[納金]せよ

ERB\SHOP2.ERB(206行目
	PRINTFORML {DAY}日目 \@ TIME ? 夜 # 昼 \@ 残り資金(%MONEY_FORM(MONEY)%円)
↓
	PRINTFORML {DAY}日目 \@ TIME ? 夜 # 昼 \@ 残り資金(%MONEY_FORM(MONEY)%朱)

ERB\SHOP2.ERB(225行目
				LOCALS = %LOCALS%(%MONEY_FORM(FLAG:(999+LOCAL))%円)
↓
				LOCALS = %LOCALS%(%MONEY_FORM(FLAG:(999+LOCAL))%朱)

ERB\SHOP2.ERB(295行目
	PRINTFORML 価格$\@ LOCAL:3 ? {MONEY/2} # {FLAG:(999+LOCAL)} \@ 残り資金${MONEY}円
↓
	PRINTFORML 価格\@ LOCAL:3 ? {MONEY/2} # {FLAG:(999+LOCAL)} \@朱 残り資金{MONEY}朱

ERB\SHOP2.ERB(506行目
		PRINTFORML 所持金が{MONEY}円になった
↓
		PRINTFORML 所持甲州金が{MONEY}朱になった

ERB\SYSTEM.ERB(63行目
		PRINTBUTTON @"[ 0] START　 (100日期限で百万円を稼ぐモード 周回プレイ有)", 0
↓
		PRINTBUTTON @"[ 0] START　 (100日期限で甲州金百万朱を稼ぐモード 周回プレイ有)", 0

ERB\口上\73_燭台切光忠\KOJO_コマンド_K73.ERB(2807行目
	;主人(共犯者)でないとダメ、すでに誰かに渡してるとダメ、対象の奴隷に執着を抱いてないとダメ、10万円ないとダメ
↓
	;主人(共犯者)でないとダメ、すでに誰かに渡してるとダメ、対象の奴隷に執着を抱いてないとダメ、10万朱ないとダメ

ERB\口上\73_燭台切光忠\KOJO_コマンド_K73.ERB(2814行目
	;エンドレスモードでないとダメ、すでにクリア済みだとダメ、100万円ないとダメ
↓
	;エンドレスモードでないとダメ、すでにクリア済みだとダメ、100万朱ないとダメ

ERB\口上\87_大和守安定\KOJO_ストーリー_K87.ERB(1006行目
		PRINTFORMW 「ってことは、なに？　この指輪100万円するの？」
↓
		PRINTFORMW 「ってことは、なに？　この指輪100万朱するの？」

ERB\地の文\EVENT_M_COM.ERB(5844行目
	PRINTFORML [1] 食べ物($1000)
↓
	PRINTFORML [1] 食べ物(1000朱)

ERB\地の文\EVENT_M_COM.ERB(5846行目
	PRINTFORML [2] 日用品($2500)
↓
	PRINTFORML [2] 日用品(2500朱)

ERB\地の文\EVENT_M_COM.ERB(5848行目
	PRINTFORML [3] アクセサリ($10000)
↓
	PRINTFORML [3] アクセサリ(10000朱)

ERB\地の文\EVENT_M_COM.ERB(5850行目
	PRINTFORML [4] 服($25000)
↓
	PRINTFORML [4] 服(25000朱)

ERB\地の文\EVENT_M_COM.ERB(5852行目
	PRINTFORML [5] 高価な物($150000)
↓
	PRINTFORML [5] 高価な物(150000朱)

ERB\地の文\EVENT_M_COM.ERB(5871行目
;主人(共犯者)でないとダメ、すでに誰かに渡してるとダメ、対象の奴隷に執着を抱いてないとダメ、10万円ないとダメ
↓
;主人(共犯者)でないとダメ、すでに誰かに渡してるとダメ、対象の奴隷に執着を抱いてないとダメ、10万朱ないとダメ

ERB\地の文\EVENT_M_COM.ERB(5882行目
;エンドレスモードでないとダメ、すでにクリア済みだとダメ、100万円ないとダメ
↓
;エンドレスモードでないとダメ、すでにクリア済みだとダメ、100万朱ないとダメ

ERB\地の文\EVENT_M_COM.ERB(9030行目
		PRINTFORMW と、{TFLAG:71}円が残されていた…
↓
		PRINTFORMW と、{TFLAG:71}朱が残されていた…

ERB\労役\CONCERT.ERB(812行目
	PRINTFORMW 利潤は{S}円程度が見込めます
↓
	PRINTFORMW 利潤は{S}朱程度が見込めます

ERB\労役\CONCERT.ERB(1238行目
;写真１枚20円
↓
;写真１枚20朱

ERB\労役\CONCERT.ERB(1241行目
;見抜き１回300円
↓
;見抜き１回300朱

ERB\労役\CONCERT.ERB(1244行目
PRINTFORMW 刀剣雷舞で歌を披露した結果、{S}円の利潤が得られました
↓
PRINTFORMW 刀剣雷舞で歌を披露した結果、{S}朱の利潤が得られました

ERB\労役\LUNCH.ERB(76行目
		PRINTFORMW 所持金 {M}増加
↓
		PRINTFORMW 所持甲州金 {M}朱増加

ERB\労役\LUNCH.ERB(84行目
	PRINTFORMW 所持金 {M}増加
↓
	PRINTFORMW 所持甲州金 {M}朱増加

ERB\労役\LUNCH.ERB(248行目
		PRINTFORMW 所持金 {M}増加
↓
		PRINTFORMW 所持甲州金 {M}朱増加

ERB\労役\LUNCH_STALL.ERB(550行目
	PRINTFORMW 利潤は{S}円程度が見込めます
↓
	PRINTFORMW 利潤は{S}朱程度が見込めます

ERB\労役\LUNCH_STALL.ERB(763行目
PRINTFORMW 定食屋台で料理を売った結果、{S}円の利潤が得られた
↓
PRINTFORMW 定食屋台で料理を売った結果、{S}朱の利潤が得られた

ERB\労役\PROMISCUOUS_SEX_LIVE.ERB(1437行目
	PRINTFORMW 利潤は{S}円程度が見込めます
↓
	PRINTFORMW 利潤は{S}朱程度が見込めます

ERB\労役\PROMISCUOUS_SEX_LIVE.ERB(2074行目
PRINTFORMW ショーの収益として{S}円を得ました
↓
PRINTFORMW ショーの収益として{S}朱を得ました

ERB\労役\PROSTITUTION.ERB(1114行目
	PRINTFORMW 報酬は{S}円程度が見込めます
↓
	PRINTFORMW 報酬は{S}朱程度が見込めます

ERB\労役\PROSTITUTION.ERB(1116行目
	PRINTFORMW 報酬が0円を下回ったので、中止します
↓
	PRINTFORMW 報酬が0朱を下回ったので、中止します

ERB\労役\PROSTITUTION.ERB(1959行目
PRINTFORMW %CALLNAME:A%の娼館奉公の報酬として、{S}円を得ました
↓
PRINTFORMW %CALLNAME:A%の娼館奉公の報酬として、{S}朱を得ました

ERB\労役\PUBLIC_TOILET.ERB(1027行目
	PRINTFORML 利益は{S}円程度が見込めます
↓
	PRINTFORML 利益は{S}朱程度が見込めます

ERB\労役\PUBLIC_TOILET.ERB(1311行目
PRINTFORMW %CALLNAME:A%での公衆便所プレイで{S}円を得ました
↓
PRINTFORMW %CALLNAME:A%での公衆便所プレイで{S}朱を得ました

ERB\労役\RENTAL_SLAVE.ERB(1179行目
	PRINTFORML %CALLNAME:A%のレンタル基本額は{S}円になります
↓
	PRINTFORML %CALLNAME:A%のレンタル基本額は{S}朱になります

ERB\労役\RENTAL_SLAVE.ERB(1181行目
	PRINTFORMW レンタル額が0円を下回ったので、中止します
↓
	PRINTFORMW レンタル額が0朱を下回ったので、中止します

ERB\労役\RENTAL_SLAVE.ERB(2216行目
PRINTFORMW %CALLNAME:A%のレンタル額として{S}円を得ました
↓
PRINTFORMW %CALLNAME:A%のレンタル額として{S}朱を得ました

ERB\労役\WORK.ERB(1029行目
PRINTFORML %NAME:TARGET%は{S}円で売れそうです
↓
PRINTFORML %NAME:TARGET%は{S}朱で売れそうです

ERB\労役\WORK.ERB(1041行目
		PRINTFORMW 結果、%NAME:TARGET%は{S}円で売れました
↓
		PRINTFORMW 結果、%NAME:TARGET%は{S}朱で売れました

ERB\労役\WORK.ERB(1255行目
PRINTFORML 録画したビデオは{TFLAG:36}円程度の値が付きそうだ
↓
PRINTFORML 録画したビデオは{TFLAG:36}朱程度の値が付きそうだ

ERB\労役\WORK.ERB(1264行目
	PRINTFORML 調教時に録画したビデオを売って、{TFLAG:36}円手に入れました
↓
	PRINTFORML 調教時に録画したビデオを売って、{TFLAG:36}朱手に入れました

ERB\労役\WORK.ERB(1502行目
	PRINTFORMW 所持金 {O}増加
↓
	PRINTFORMW 所持甲州金 {O}朱増加

────

このパッチのパッチまとめ等への取り込みはご自由にどうぞ

────

パッチ製作：しんしゅう
したらばの調子が悪い時などはこちらへ　@shinsshu_are
