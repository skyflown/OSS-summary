브랜치 리베이스 rebase

공통 조상 base

$git rebase master
재배치 rebase 병합 수행
base를 수정

rebase를 이용한 브랜치 병합 과정
이후 다시 fast-forward 병합 수행
$git rebase master
$git merge bugfix

충돌 발생 후 해결 절차
1. 파일 수정
2. 파일 추가
3. rebase 계속 수행, 마지막 메시지 수정

merge
여러 분기가 생긴 변경 내용의 이력이 모두 그대로 남아 있기 때문에 이력이 복잡해짐

rebase
히스토리가 선형으로 단순해지고 좀 더 깨끗한 이력을 남김
원래의 커밋 이력이 변경됨, 정확한 이력을 남겨야 할 필요가 있을 경우에는 사용하면 안됨

fast-forward와 rebase 비교
fast-forward merge
조상에 위치한 브랜치에서 선행 브랜치의 마지막으로 이동하는 병합
rebase
두 갈래의 브랜치에서 기존의 베이스를 수정 
병합할 브랜치 마지막 커밋을 새로운 베이스로 수정하는 병합

$git rebase <newparent><branch>

커밋 이력 수정

• 최근 커밋 내용 수정
HEAD의 내용 수정

커밋 옵션 --amend 사용
$git commit --amend -> 기본 편집기로 메시지 편집
$git commit --amend -m 'new message' -> 명령어 상에 직접 메시지 입력
$git commit --amend --no--edit -> 메시지 수정 없이 다시 커밋 수정

rebase --interactive
$git rebase -i HEAD~3
- > $git rebase --interactive HEAD~3
HEAD~3: 수정할 커밋의 직전 커밋
실제 HEAD~2부터 수정 가능, 오래된 커밋부터 표시

주요 rebase -i 대화형 명령어
p(ick): 해당 커밋을 수정하지 않고 그대로 사용
r(eword): 개별 커밋 메시지를 다시 작성
s(quash): 계속된 이후 커밋을 다시 이전 커밋에 결합
d(rop): 커밋 자체를 삭제

더 최신의 커밋을 이전 커밋에 뭉치는 방법
상위에 위지한 커밋에 pick이 있으면서
아래로 연속적으로 squash명형, 다음으로 커밋 E가 커밋 BB에 뭉쳐져 커밋 E가 제게됨

새로운 커밋 메시지 입력하는 단계
기본 편집기로 편집

