브랜치 병합

병합
두 개의 브랜치를 하나로 모으는 과정
fast-forward(빨리 감기) 병합, 3-awy 병합

fast-forward 병합 조건
현재 브랜치 master가 병합할 대상 커밋의 직접적인 뿌리가 되는 경우
간단히 두 브랜치가 일렬 상태
$ git merge bugfix

3-way 상태: 두 분기가 갈라진 상태
두 브랜치의 조상이 같은 경우
master 브랜치 내의 변경 내용과 bugfix 브랜치 내의 변경 내용을 하나로 통합할 필요
3-way 병합
새로운 커밋을 사용하여 두 기록을 합침

3-way 병합 수행
새로운 커밋 E 생성
$ git merge bugfix
$ git merge bugfix -m 'merge msg'
m이 없으면 메시지 입력할 기본 편집기 실행

일렬 상태 기본 fast forward 병합

3-wat 병합
옵션 --no--ff
$git merge dev1 --no--ff

$git merge --no--ff -> 무조건 3-way 병합
$git merge {병합할 브랜치 명} -> 보통의 병합
$git merge --ff--only -> fast-forward 병합
$git merge --squash -> 현재 브랜치에 병합 대상과의 합치는 커밋을 하나 생성해 병합
$git merge --squash hotfix -> 강압적인? 병합

병합 충돌
병합할 두 브랜치 마지막 커밋을 비교
두 브랜치 모두에서 변경 사항이 달리 발생한 파일
두 브랜치에서 모두 수정되었으므로 어느 것을 사용해야할지 결정 못하는 상황

충돌 해결
직접 파일 내용을 수정 후 저장
add, commit 진행
필요하면 합병된 이전 브랜치 삭제

1. 저장소 mconf 생성 후 이동
2. 파일 f 생성 후 커밋
3. 브랜치 topic 생성 후 이동
4. 파일 f 수정 후 커밋
5. 브랜치 main으로 이동
6. 파일 f 수정후 커밋
7. 현재 모든 브랜치 로그 이력 보기

8. 병합 실행해 충돌 발생
9. 코드 수정
코드 수정 후 반드시 커밋 필요
10. 충돌 해결을 위한 커밋
11. 병합 후 로그 이력 그래프
12. 병합된 파일 확인
충돌한 파일 내부 표시(3개)
<<<<<<< HEAD
현재 브랜치 HEAD의 수정 내용
=======
병합되는 브랜치 feat/list의 수정 내용
>>>>>>> feat/list

병합 취소
$git merge --abort

다시 병합
$git merge feat/list
