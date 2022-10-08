eraToloveA용사야카 패치

■도입 방법■
eraToLoveA02용 패치 통계 20190410
eraToLoveA02 통계 20191104
eraToloveA20191207 패치
eraToloveA20191229 패치
이상을 적용한 eraToLoveA02 본체(이하 본체)를 준비해 주세요
당패치의 각 폴더를 본체내의 각 폴더에 덧쓰기해 주세요

────

패치 내용

버그 수정
난이도의 표기를 일부 변경
소지금,엔,$,엽전을 코우슈우금/고슈금에 통일

────

이하 변경점

CSV\Talent.csv(28,29행째
21,무관심,:ABL:봉사정신가 올리기 어렵다. PALAM:순종,욕정,굴복,공포,반감가 오르기 어렵다
22,감정부족,:ABL:봉사정신가 올리기 어렵다. PALAM가 전체적으로 오르기 어렵다
↓
21,무관심,;ABL:봉사정신가 올리기 어렵다. PALAM:순종,욕정,굴복,공포,반감가 오르기 어렵다
22,감정부족,;ABL:봉사정신가 올리기 어렵다. PALAM가 전체적으로 오르기 어렵다
※본래;로 comment out 해야 할 부분이:(이)가 되어 있던 것을 수정

ERB\SYSTEM.ERB(23행째
SAVESTR:0 = /240/241/242/
↓
SAVESTR:0 = /390/391/392/
※커맨드 번호의 변경에 맞추어 수정

ERB\INFO.ERB(48행째
		PRINT 보통
↓
		PRINT 보

ERB\INFO.ERB(481행째
	PUTFORM 스구루 
↓
	PUTFORM 역 

ERB\INFO.ERB(483행째
	PUTFORM 보통 
↓
	PUTFORM 보 

CSV\_Replace.csv(8행째
돈의 단위,엔
↓
돈의 단위,고슈금

CSV\Str.csv(89행째
572,「당신이 그것들을 바탕으로 기일까지 100만엔을 준비하겠다」
↓
572,「당신이,그것들을 원손에,기일까지 코우슈우금 100만고슈금를 준비한다」

ERB\DEBUGMENU.ERB(82행째
PRINTL [34] - 소지금을 변경한다
↓
PRINTL [34] - 소지 코우슈우금을 변경한다

ERB\DEBUGMENU.ERB(1281행째
PRINTFORML 현재의 소지금${MONEY}
↓
PRINTFORML 현재의 소지 코우슈우금{MONEY}고슈금

ERB\DEBUGMENU.ERB(1295행째
PRINTFORMW 소지금을${MONEY}로 변경했습니다
↓
PRINTFORMW 소지 코우슈우금을{MONEY}고슈금로 변경했습니다

ERB\ENDING.ERB(82행째
		PRINTFORMW 최종적으로는,「100일」이내에 「100만엔」을 버는 것이 목적입니다.
↓
		PRINTFORMW 최종적으로는,「100일」이내에 「100만고슈금」를 버는 것이 목적입니다.

ERB\ENDING.ERB(90,91행째
	PRINTFORMW 그 기간을 지나면,노예의 유지비등으로,매일 아침 소지금이 줄어들어 갑니다.
	PRINTFORMW 소지금이 바닥을 다하면 게임 오버로 되기 때문에,
↓
	PRINTFORMW 그 기간을 지나면,노예의 유지비등으로,매일 아침 소지 코우슈우금이 줄어들어 갑니다.
	PRINTFORMW 소지 코우슈우금이 바닥을 다하면 게임 오버로 되기 때문에,

ERB\EVENT_S.ERB(104행째
	PRINTFORML 노예와 도구의 유지비,생활비에${A}걸렸다……
↓
	PRINTFORML 노예와 도구의 유지비,생활비에{A}고슈금 걸렸다……

ERB\INFO.ERB(39,40행째
;소지 엽전　
PRINTFORM 소지 엽전:{MONEY}　
↓
;소지 코우슈우금
PRINTFORM 소지 코우슈우금:{MONEY}고슈금　

ERB\ITEM.ERB(324행째
	LOCALS = [{LOCAL,2}] %ITEMNAME:LOCAL%(%MONEY_FORM(ITEMPRICE:LOCAL)%엔)
↓
	LOCALS = [{LOCAL,2}] %ITEMNAME:LOCAL%(%MONEY_FORM(ITEMPRICE:LOCAL)%고슈금)

ERB\ITEM.ERB(1102행째
PRINTFORML 소지금:{MONEY}엔
↓
PRINTFORML 소지 코우슈우금:{MONEY}고슈금

ERB\SHOP.ERB(80행째
	PRINTFORML 　(소지 엽전{MONEY})
↓
	PRINTFORML 　(소지 코우슈우금{MONEY}고슈금)

ERB\SHOP.ERB(138행째
		PRINTFORML 목표:100일 이내에$1000000벌어,[납금]해
↓
		PRINTFORML 목표:100일 이내에 코우슈우금 1000000고슈금 벌어,[납금]해

ERB\SHOP2.ERB(206행째
	PRINTFORML {DAY}일째 \@ TIME ? 야 # 주 \@ 나머지 자금(%MONEY_FORM(MONEY)%엔)
↓
	PRINTFORML {DAY}일째 \@ TIME ? 야 # 주 \@ 나머지 자금(%MONEY_FORM(MONEY)%고슈금)

ERB\SHOP2.ERB(225행째
				LOCALS = %LOCALS%(%MONEY_FORM(FLAG:(999+LOCAL))%엔)
↓
				LOCALS = %LOCALS%(%MONEY_FORM(FLAG:(999+LOCAL))%고슈금)

ERB\SHOP2.ERB(295행째
	PRINTFORML 가격$\@ LOCAL:3? {MONEY/2} # {FLAG:(999+LOCAL)} \@ 나머지 자금${MONEY}엔
↓
	PRINTFORML 가격\@ LOCAL:3? {MONEY/2} # {FLAG:(999+LOCAL)} \@고슈금 나머지 자금{MONEY}고슈금

ERB\SHOP2.ERB(506행째
		PRINTFORML 소지금이{MONEY}엔이 되었다
↓
		PRINTFORML 소지 코우슈우금이{MONEY}고슈금가 되었다

ERB\SYSTEM.ERB(63행째
		PRINTBUTTON @"[ 0] START　 (100일 기한에 백만엔을 버는 모드 주회 플레이유)",0
↓
		PRINTBUTTON @"[ 0] START　 (100일 기한에 코우슈우금백만고슈금를 버는 모드 주회 플레이유)",0

ERB\입상\73_쇼쿠다이키리 미츠타다\KOJO_커맨드_K73.ERB(2807행째
	;주인(공범자)이 아니면 안돼,벌써 누군가에게 건네주고 있으면 안돼,대상의 노예에게 집착을 안지 않았다고 안돼,10만엔 없으면 안돼
↓
	;주인(공범자)이 아니면 안돼,벌써 누군가에게 건네주고 있으면 안돼,대상의 노예에게 집착을 안지 않았다고 안돼,10만고슈금 없으면 안돼

ERB\입상\73_쇼쿠다이키리 미츠타다\KOJO_커맨드_K73.ERB(2814행째
	;엔드리스 모드가 아니면 안돼,벌써 클리어가 끝난 상태라면 안돼,100만엔 없으면 안돼
↓
	;엔드리스 모드가 아니면 안돼,벌써 클리어가 끝난 상태라면 안돼,100만고슈금 없으면 안돼

ERB\입상\87_야마토노카미 야스사다\KOJO_스토리_K87.ERB(1006행째
		PRINTFORMW 「라는 것은,뭐? 이 반지 100만엔 하는 거야?」
↓
		PRINTFORMW 「라는 것은,뭐? 이 반지 100만고슈금 하는 거야?」

ERB\지문\EVENT_M_COM.ERB(5844행째
	PRINTFORML [1] 음식($1000)
↓
	PRINTFORML [1] 음식(1000고슈금)

ERB\지문\EVENT_M_COM.ERB(5846행째
	PRINTFORML [2] 일용품($2500)
↓
	PRINTFORML [2] 일용품(2500고슈금)

ERB\지문\EVENT_M_COM.ERB(5848행째
	PRINTFORML [3] 악세사리($10000)
↓
	PRINTFORML [3] 악세사리(10000고슈금)

ERB\지문\EVENT_M_COM.ERB(5850행째
	PRINTFORML [4] 옷($25000)
↓
	PRINTFORML [4] 옷(25000고슈금)

ERB\지문\EVENT_M_COM.ERB(5852행째
	PRINTFORML [5] 고가의 물건($150000)
↓
	PRINTFORML [5] 고가의 물건(150000고슈금)

ERB\지문\EVENT_M_COM.ERB(5871행째
;주인(공범자)이 아니면 안돼,벌써 누군가에게 건네주고 있으면 안돼,대상의 노예에게 집착을 안지 않았다고 안돼,10만엔 없으면 안돼
↓
;주인(공범자)이 아니면 안돼,벌써 누군가에게 건네주고 있으면 안돼,대상의 노예에게 집착을 안지 않았다고 안돼,10만고슈금 없으면 안돼

ERB\지문\EVENT_M_COM.ERB(5882행째
;엔드리스 모드가 아니면 안돼,벌써 클리어가 끝난 상태라면 안돼,100만엔 없으면 안돼
↓
;엔드리스 모드가 아니면 안돼,벌써 클리어가 끝난 상태라면 안돼,100만고슈금 없으면 안돼

ERB\지문\EVENT_M_COM.ERB(9030행째
		PRINTFORMW 와{TFLAG:71}엔이 남아 있었다…
↓
		PRINTFORMW 와{TFLAG:71}고슈금가 남아 있었다…

ERB\노역\CONCERT.ERB(812행째
	PRINTFORMW 이윤은{S}엔정도를 전망할 수 있습니다
↓
	PRINTFORMW 이윤은{S}고슈금정도를 전망할 수 있습니다

ERB\노역\CONCERT.ERB(1238행째
;사진 1매 20엔
↓
;사진 1매 20고슈금

ERB\노역\CONCERT.ERB(1241행째
;간파해 1회 300엔
↓
;간파해 1회 300고슈금

ERB\노역\CONCERT.ERB(1244행째
PRINTFORMW 도검뢰무로 노래를 피로[披露] 한 결과,{S}엔의 이윤을 얻을 수 있었습니다
↓
PRINTFORMW 도검뢰무로 노래를 피로[披露] 한 결과,{S}고슈금의 이윤을 얻을 수 있었습니다

ERB\노역\LUNCH.ERB(76행째
		PRINTFORMW 소지금 {M}증가
↓
		PRINTFORMW 소지 코우슈우금 {M}고슈금증가

ERB\노역\LUNCH.ERB(84행째
	PRINTFORMW 소지금 {M}증가
↓
	PRINTFORMW 소지 코우슈우금 {M}고슈금증가

ERB\노역\LUNCH.ERB(248행째
		PRINTFORMW 소지금 {M}증가
↓
		PRINTFORMW 소지 코우슈우금 {M}고슈금증가

ERB\노역\LUNCH_STALL.ERB(550행째
	PRINTFORMW 이윤은{S}엔정도를 전망할 수 있습니다
↓
	PRINTFORMW 이윤은{S}고슈금정도를 전망할 수 있습니다

ERB\노역\LUNCH_STALL.ERB(763행째
PRINTFORMW 정식포장마차로 요리를 판 결과,{S}엔의 이윤을 얻을 수 있었다
↓
PRINTFORMW 정식포장마차로 요리를 판 결과,{S}고슈금의 이윤을 얻을 수 있었다

ERB\노역\PROMISCUOUS_SEX_LIVE.ERB(1437행째
	PRINTFORMW 이윤은{S}엔정도를 전망할 수 있습니다
↓
	PRINTFORMW 이윤은{S}고슈금정도를 전망할 수 있습니다

ERB\노역\PROMISCUOUS_SEX_LIVE.ERB(2074행째
PRINTFORMW 쇼의 수익으로 해서{S}엔을 얻었습니다
↓
PRINTFORMW 쇼의 수익으로 해서{S}고슈금를 얻었습니다

ERB\노역\PROSTITUTION.ERB(1114행째
	PRINTFORMW 보수는{S}엔정도를 전망할 수 있습니다
↓
	PRINTFORMW 보수는{S}고슈금정도를 전망할 수 있습니다

ERB\노역\PROSTITUTION.ERB(1116행째
	PRINTFORMW 보수가 0엔을 밑돌았으므로,중지합니다
↓
	PRINTFORMW 보수가 0고슈금를 밑돌았으므로,중지합니다

ERB\노역\PROSTITUTION.ERB(1959행째
PRINTFORMW %CALLNAME:A%의 창관봉공의 보수로서{S}엔을 얻었습니다
↓
PRINTFORMW %CALLNAME:A%의 창관봉공의 보수로서{S}고슈금를 얻었습니다

ERB\노역\PUBLIC_TOILET.ERB(1027행째
	PRINTFORML 이익은{S}엔정도를 전망할 수 있습니다
↓
	PRINTFORML 이익은{S}고슈금정도를 전망할 수 있습니다

ERB\노역\PUBLIC_TOILET.ERB(1311행째
PRINTFORMW %CALLNAME:A%에서의 공중 변소 플레이로{S}엔을 얻었습니다
↓
PRINTFORMW %CALLNAME:A%에서의 공중 변소 플레이로{S}고슈금를 얻었습니다

ERB\노역\RENTAL_SLAVE.ERB(1179행째
	PRINTFORML %CALLNAME:A%의 렌탈 기본액은{S}엔이 됩니다
↓
	PRINTFORML %CALLNAME:A%의 렌탈 기본액은{S}고슈금가 됩니다

ERB\노역\RENTAL_SLAVE.ERB(1181행째
	PRINTFORMW 렌탈액수가 0엔을 밑돌았으므로,중지합니다
↓
	PRINTFORMW 렌탈액수가 0고슈금를 밑돌았으므로,중지합니다

ERB\노역\RENTAL_SLAVE.ERB(2216행째
PRINTFORMW %CALLNAME:A%의 렌탈 이마로서{S}엔을 얻었습니다
↓
PRINTFORMW %CALLNAME:A%의 렌탈 이마로서{S}고슈금를 얻었습니다

ERB\노역\WORK.ERB(1029행째
PRINTFORML %NAME:TARGET%는{S}엔으로 팔릴 것 같습니다
↓
PRINTFORML %NAME:TARGET%는{S}고슈금로 팔릴 것 같습니다

ERB\노역\WORK.ERB(1041행째
		PRINTFORMW 결과,%NAME:TARGET%는{S}엔으로 팔렸습니다
↓
		PRINTFORMW 결과,%NAME:TARGET%는{S}고슈금로 팔렸습니다

ERB\노역\WORK.ERB(1255행째
PRINTFORML 녹화한 비디오는{TFLAG:36}엔 정도의 값이 붙을 것 같다
↓
PRINTFORML 녹화한 비디오는{TFLAG:36}고슈금정도의 값이 붙을 것 같다

ERB\노역\WORK.ERB(1264행째
	PRINTFORML 조교시에 녹화한 비디오를 팔아,{TFLAG:36}엔손에 넣었습니다
↓
	PRINTFORML 조교시에 녹화한 비디오를 팔아,{TFLAG:36}고슈금손에 넣었습니다

ERB\노역\WORK.ERB(1502행째
	PRINTFORMW 소지금 {O}증가
↓
	PRINTFORMW 소지 코우슈우금 {O}고슈금증가

────

이 패치의 패치 통계등에의 혼잡은 자유롭게 아무쪼록

────

패치 제작:해 사람들
한다면의 상태가 나쁠 때 따위는 이쪽으로@shinsshu_are
