# I'm an early 🐤

<p align="center">
  <img src="https://user-images.githubusercontent.com/9604647/87132487-ee95c400-c2d0-11ea-983b-70dce61fba82.png" alt="screenshot" width="500">
  <h3 align="center">📌✨productive-box 로 Github Profile 꾸미기</h3>
</p>

---

## 설정 방법

환경변수 `GH_TOKEN`, `GIST_ID` 를 설정하고 clone 받은 저장소에서 설정한 환경변수로 입력한다.

1. `GH_TOKEN` 얻기
    - 토큰 생성: https://github.com/settings/tokens/new
    - "Note" 입력: 아무거나 입력해도 상관 없고 나는 productive-box 로 함
    - "Select scopes" 체크: repo, gist 체크
    - "Generate Token" 버튼 클릭
    - 생성된 토큰을 복사 후 어디 적어두어야 함(페이지 이동 시 사라지고 다시 알 수 없음)

2. `GIST_ID` 얻기
    - gist 생성 아무 description 아무 내용 입력 https://gist.github.com/
    - "Create public gist" 버튼 클릭
    - 생성된 GIST_ID 복사 (url `https://gist.github.com/xx4159/{{ GIST_ID }}` 에서 맨 뒤에 있는 값)

3. `GH_TOKEN` 입력
    - clone https://github.com/maxam2017/productive-box
    - clone 받은 저장소 > Settings 탭 이동 > Secrets 메뉴 이동
    - "New secret" 버튼 클릭
    - "Name", "Value" 입력
        - Name: "GH_TOKEN"
        - Value: 1번 과정에서 얻은 `GH_TOKEN` 값 입력

4. `GIST_ID` 입력
    - clone 받은 저장소 > Settings 탭 이동 > Secrets 메뉴 이동
    - "New secret" 버튼 클릭
    - "Name", "Value" 입력
        - Name: "GIST_ID"
        - Value: 2번 과정에서 얻은 `GIST_ID` 값 입력
    - 저장소의 Code 탭으로 이동하여 ".github/workflows/schedule.yml"  파일을 아래 내용으로 수정하고 커밋 후 master로 푸시 한다
        - ```yml
            GIST_ID: ${{ secrets.GIST_ID }}
            TIMEZONE: Asia/Seoul
            ```
        - cron 으로 0시 0분마다 스케쥴이 돌아서 업데이트 되거나 master 에 push 했을 때 반영 되도록 되어있어서 일부러 master push 작업을 남겨두고 수정함

5. 자신의 github profile 페이지로 이동하여 "Customize your pins" 를 눌러보면 "I'm an early 🐤" 를 확인할 수 있고 체크하면 화면에 노출된다. 끝
