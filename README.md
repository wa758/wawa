# wawa

`git clone git@github.com:wa758/wawa.git`

 새 브랜치 만들기 
git branch name

 만든 브랜치로 이동하기
git checkout name

 꿀팁
git checkout -b name라고 입력하면 만들기와 이동을 한 번에 할 수 있습니다.

 1. 파일 진짜로 만들기 (이제 ls를 치면 welcome.txt가 보일 거예요)
echo "프로젝트 첫 번째 브랜치 연습" > welcome.txt

 2. 깃에 올릴 준비 (장바구니에 담기)
git add welcome.txt

 3. 확정 짓기 (라벨 붙이기)
git commit -m "Add: welcome file to vtol branch"

 4. 깃허브 서버로 발사!
git push origin vtol
