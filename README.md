# wawa

`git clone git@github.com:wa758/wawa.git`

조직 저장소일 때: git@github.com:DGU_DAVI/flight_control_2026.git

개인 저장소일 때: git@github.com:wa758/flight_control_2026.git

폴더 진입: `cd flight_control_2026`


 새 브랜치 만들기 
`git branch name`

 만든 브랜치로 이동하기
`git checkout name`

 꿀팁
`git checkout -b name`라고 입력하면 만들기와 이동을 한 번에 할 수 있습니다.

 1. 파일 진짜로 만들기 (이제 ls를 치면 welcome.txt가 보일 거예요)
`echo "프로젝트 첫 번째 브랜치 연습" > welcome.txt`

 2. 깃에 올릴 준비 (장바구니에 담기)
`git add welcome.txt`

 3. 확정 짓기 (라벨 붙이기)
`git commit -m "Add: welcome file to vtol branch"`

 4. 깃허브 서버로 발사!
`git push origin name`

Pull의 핵심 개념

가져오기 + 합치기: 서버에 있는 최신 데이터를 다운로드함과 동시에, 내가 작업하던 코드와 자동으로 합쳐줍니다(Merge).

팀 프로젝트의 필수: 팀원들이 자율주행 드론 코드를 수정해서 GitHub에 올렸다면, 재경님이 pull을 해야만 그 최신 코드가 재경님 노트북에 반영됩니다.

명령어: 터미널에서는 주로 `git pull origin main` (또는 브랜치명)을 입력해서 실행합니다.

⚔️ Git Conflict란?

두 명 이상의 팀원이 같은 파일의 같은 부분을 동시에 수정하고 GitHub에 합치려 할 때, Git이 "어느 쪽 코드가 맞는지 모르겠어!"라며 판단을 보류하는 상태를 말합니다.
🛠️ 충돌 해결 과정 (팀장 가이드)

    충돌 발생 확인: git pull이나 git merge를 했을 때 "CONFLICT (content): Merge conflict in [파일명]"이라는 메시지가 뜨면 충돌이 난 겁니다.

    파일 수정: 충돌이 난 파일을 열면 아래와 같은 특수 기호가 보입니다.

        <<<<<<< HEAD: 내가 수정한 코드

        =======: 구분선

        >>>>>>> [브랜치명]: 팀원이 수정한 코드

    코드 선택: 두 코드 중 살릴 부분을 고르고 특수 기호들을 모두 지워준 뒤 저장합니다.

    다시 커밋: 수정이 끝났다면 git add → git commit → git push 순서로 마무리합니다.
