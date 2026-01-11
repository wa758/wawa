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

📥 Git Fetch의 핵심 개념

정보만 가져오기: GitHub 서버에 팀원(박인성, 김민재 등)이 올린 새로운 코드나 브랜치가 있는지 데이터만 슥 가져옵니다.

내 코드는 안전: fetch만 하면 재경님이 지금 노트북에서 작성 중인 코드 파일에는 아무런 변화가 생기지 않습니다. 즉, 안전하게 변경 사항을 미리 보기 할 때 사용합니다.

Pull과의 관계: 사실 git pull은 git fetch를 먼저 실행해서 정보를 가져온 다음, 곧바로 내 코드와 합치는 git merge를 합친 명령어입니다.

`git fetch origin`

Pull의 핵심 개념

가져오기 + 합치기: 서버에 있는 최신 데이터를 다운로드함과 동시에, 내가 작업하던 코드와 자동으로 합쳐줍니다(Merge).

팀 프로젝트의 필수: 팀원들이 자율주행 드론 코드를 수정해서 GitHub에 올렸다면, 재경님이 pull을 해야만 그 최신 코드가 재경님 노트북에 반영됩니다.

명령어: 터미널에서는 주로 `git pull origin main` (또는 브랜치명)을 입력해서 실행합니다.

🛠️ 재경님을 위한 실전 Revert 사용법

    되돌릴 커밋 확인: git log --oneline을 입력해서 취소하고 싶은 커밋의 ID(예: a3882f2)를 찾습니다.

    명령어 실행: git revert [커밋ID]를 입력합니다.

    메시지 작성: 취소 사유를 적는 편집창이 뜨면 내용을 적고 저장합니다.

    확인: 이제 first.txt에 썼던 "메롱"이 사라지고, 기록에는 "Revert 'Add: first branch'"라는 새 커밋이 생겼을 거예요.

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
