오픈소스 소프트웨어
 OSS: open source software 오픈소스
-> 누구나 특별한 제한 없이 그 코드를 보고 사용할 수 있는 오픈소스 라이선스를 만족하는 SW

OSI: open source Initiative
-> 공개 소스 정의의 관리 및 촉진을 담당하는 비영리 조합

자유 소프트웨어 (Free Software)

오픈소스 지원 관리 서버
소스코드를 통해 여러 개발자 협업

협업 방식
-> 서로 간에 소스코드를 사용, 변경 및 공유할 수 있도록 커뮤니티 프로덕션과 동료 평가에 의존
-> 개발자들은 보다 혁신적인 소프트웨어 솔루션을 만들기 위해 인사이트, 아이디어 및 코드를 공유

-> 누구든 보다 쉽게 연구하여, 새로운 프로그래밍 기술을 개발
-> 공개의 의무, 품질보증 및 유지보수, 보안 등의 어려움

LAMP
-> Linux : 세계 최대 규모의 오픈소스 프로젝트
-> Apache : 오픈소스 크로스 플랫폼 웹 서버
-> MySQL : 오픈소스 관계형 데이터베이스 관리 시스템
-> PHP : 범용 스크립팅 언어

오픈소스 라이선스 저작권

GPL
자유소프트웨어재단에서 만든 라이선스
가장 많이 알려진 카피레프트에 속한 라이선스
프로그램은 목적이나 형태의 제한없이 사용이 가능
프로그램을 이후 수정하고 배포하는 모든 경우에 무조건 GPL로 공개를 해야 함
ex) 리눅스 커널, Git, 마리아 DB, 워드프레스, 파이어폭스(v2.0) 등

AGPL 
GPL을 기반으로 만든 라이선스
네트워크로 상호 작용하는 소프트웨어의 소스코드도 공개해야 한다는 조항을 추가한 라이선스
ex) 몽고 DB 등

LGPL
보다 완화된 GPL 라이선스
GPL로 공개해야 하는 부담 때문에 실무에서 사용되기 어려운 점을 보완하기 위해 만들어진 라이선스
전체 소스코드를 공개하지 않고 사용된 오픈소스 라이브러리에 대한 소스코드만 공개
ex) 파이어폭스(v2.1) 등

Apache License
소스코드 공개에 다한 의무사항은 라이선스에 포함되어 있지 않음
아파치 라이선스 버전 2.0을 꼭 포함시켜야 하고 아파치재단의 소프트웨어라는 사실을 명시
ex) 안드로이드, 하둡 등

MIT License
MIT에서 학생들을 지원하기 위해서 만든 라이선스
가장 느슨한 조건을 가지고 있어서 많은 사람들이 사용하기 용이
ex) 부트스트랩, Angular.js, Backbone.js, jQuery

임시 저장 stash
커밋 할 필요 없이 파일의 변경 사항을 숨기거나 비밀리에 저장할 수 있는 강력한 도구
Stack of git stashes

$git stash
$git stash -m '메세지' 
$git stash save
$git stash save '메세지'

--keep-index, -k
스테이징 영역은 제외하고 작업 폴더만 저장
--include-untracked, -u
Untracked 파일도 포함해 저장
--patch , -p
자신이 stash에 저장할 파일과 저장하지 않을 파일을 지정 가능

$git stash apply -> 작업 디렉토리 내용만 복사
$git stash apply --index -> 스테이지 영역도 함께 복사

목록 보기
가장 최신 것이 0번

$ git stash list
stash@{0} < 가장 최신 것이 0번
stash@{1}
stash@{2}
...

해당 stash 항목이 생성되었을 때 커밋 자료와 최신 stash 항목 간의 차이 표시
-> $git stash show
변화된 파일과 변화된 수만 표시

-> $git stash show -p
-p : 파일 내용의 차이까지 보이기

-> $git stash show stash@{n}
-> $git stash show stash@{n} -p

임시 저장된 stash 반영

최근 또는 지정된 임시저장소 내용을 가져와 반영하고 삭제
$git stash pop
$git stash pop stash@{n}

최근 또는 지정된 임시저장소 내용을 가져와 반영, 작업 디렉토리만 반영, stash 목록은 그대로
$git stash apply
$git stash apply stash@{n}

최근 또는 지정된 임시저장소 내용을 가져와 반영, 작업 디렉토리와 스테이징 영역도 반영, stash 목록은 그대로
$git stash apply --index
$git stash apply --index stash@{n}

특정 stash 삭제와 모든 stash 삭제
최근 임시저장 내용을 삭제
$git stash drop

지정된 임시저장 내용을 삭제
$git stash drop stash@{n}

모든 stash 목록을 모두 제거
$git stash clear

Untracted 파일 삭제
$git clean -> 바로 삭제되지 않음

$git clean -f -> 무조건 삭제