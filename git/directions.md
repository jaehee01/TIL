- git init
    - 로컬 저장소 설정(초기화)
- git add
    - 변경사항이 있는 파일을 staging area에 추가
- git commit
    - staging area에 있는 파일을 저장소에 기록
- git status
    - 파일 상태 확인
    
    **Tracked**: Git이 해당 파일을 추적 및 관리하는 상태
    **Untracked**:  반대로 아직 Git이 해당 파일을 추적 및 관리하지 않는 상태
    
    **Unmodified:** Commit을 모두 마친 상태이며 Commit은 깃에 내가 만든 코드를 저장을 완료한 상태
    
    **Modified:** Git으로 **관리되고 있던** 코드를 수정하여 변경이 일어난 상태. Unmodified상태의 파일을 수정하면 아래 이미지와 같이 Modified상태가 됩니다. `git status` 명령어의 결과를 주의깊게 봅니다. 하지만 `Unstaged`상태 이기때문에 아직 commit을 할수 없습니다.
    
    Modified상태는 `Unstaged` 상태에서는 커밋을 할수 없으며 `git add` 명령어를 통해서 파일을 `Staged` 상태로 만들어주면 커밋이 가능합니다.
    `Unstaged`상태였던 파일을 `git add` 명령어를 통해 `Staged`상태로 변경시켜주었으며 이제 커밋할 준비가 됬습니다.
    
    ```bash
    SSAFY@2□□166 MINGW64 ~/Desktop/git_commit (master)
    $ git status a.txt
    On branch master
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   a.txt
    
    SSAFY@2□□166 MINGW64 ~/Desktop/git_commit (master)
    $ git add a.txt
    
    SSAFY@2□□166 MINGW64 ~/Desktop/git_commit (master)
    $ git status a.txt
    On branch master
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            modified:   a.txt
    ```
    
- git add 파일명
    - 파일을 staging area에 추가하기
- git commit -m “커밋명”
    - commit 생성하기
    
    첫 사용시 작성자 정보 설정해야 함
    
    - git config - -global [user.email](http://user.email) “메일주소”
    - git config - -global [user.name](http://user.name) “유저네임”
    
    커밋 이력이 없으면 push가 안됨
    
- git log
    - commit 목록(history) 확인

vim 에디터를 통해 commit 수정 가능

- git push origin master
    - 원격 저장소에 commit 목록 업로드

### git commit

**🌟 코드 변경 후 저장 → git add 파일명→ git commit -m “커밋명”→ git push origin master**

(상태 확인은 git status 파일명)

**원격저장소 - github**

- git pull origin master
    - 원격 저장소의 변경사항만을 받아옴
- git clone remote_repo_url
    - 원격 저장소 전체를 복제

### git pull&clone

원격 저장소를 복제

- git clone 원격저장소 주소

→ 기존 폴더의 파일에서 새로운 커밋을 생성하고 원격저장소에 push 

- git push origin master

→ 복제한 폴더에서 업데이트된 사항 받기

- git pull

### gitignore

git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는 데 사용되는 텍스트 파일
