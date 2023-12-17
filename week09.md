
깃허브 원격 저장소 생성

저장소이름 git-clone
https 주소 복사

원격 저장소 복제
$ git clone [복사된 주소] -> 동일한 이름
$ git clone [복사된 주소] [새로운 폴더명] 하부 폴더 [새로운-폴더명] 이름으로 복제
$ git clone [복사된 주소] . -> 현재 폴더에 복제

원격 저장소 관리 코드
$ git remote -> 원격 저장소 목록, 기본 이름 origin
$ git remote -v -> 원격 저장소 주소와 이름 목록
$ git remote add origin URL -> 원격 저장소 별칭 저장
$ git remote show origin -> 자세한 정보
$ git remote rename origin org -> 이름 수정
$ got remote rm org -> 삭제

vs code로 원격 저장소 관리
Clone git repository

# 17
Working Derectory -add-> Git Local Repository -push-> <-pull- Git Server Repository

윈도 push 중 오류
- > 참조 오류 발생 가능

Windows 환경에서 깃 사용자 계정과 암호 설정 및 변경
1. 제어판 - 사용자 계정 - 자격 증명 관리자
2. Windows 자격 증명
3. 일반 자격 증명
4. git 관련 자격 증명 편집

PAT로 연결
$ git push -u https://{token}@github.com/{username}/{repo_name}.git

지역 저장소에서 push
$ git push <저장소명> <브랜치명>
옵션 -u -> 최초 한 번만 저장소명, 브랜치명 입력, 그 이후에는 모든 인자 생략 가능
$ git config --global push.default current

git pull = git fetch + git merge
fetch 명령과 merge 명령이 순차적으로 진행
fetch 명령: 원격 저장소의 정보를 로컬 저장소로 가져오는 명령, 병합X
merge 명령: 변경된 정보를 로컬 저장소의 내용과 병합

