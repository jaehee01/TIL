## git 기본 동작
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

## git commit

**🌟 코드 변경 후 저장 → git add 파일명→ git commit -m “커밋명”→ git push origin master**

(상태 확인은 git status 파일명)

**원격저장소 - github**

- git pull origin master
    - 원격 저장소의 변경사항만을 받아옴
- git clone remote_repo_url
    - 원격 저장소 전체를 복제

## git pull&clone

원격 저장소를 복제

- git clone 원격저장소 주소

→ 기존 폴더의 파일에서 새로운 커밋을 생성하고 원격저장소에 push 

- git push origin master

→ 복제한 폴더에서 업데이트된 사항 받기

- git pull

## gitignore

git에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는 데 사용되는 텍스트 파일


## git revert

특정 commit을 없었던 일로 만드는 작업(재설정)

프로젝트 기록에서 commit을 없었던 일로 처리 후 그 결과를 새로운 commit으로 추가함

- git revert <commit id>
    - revert 하기
- git log —oneline
    - commit 목록 확인(commit id 알아내기)

커밋 기록이 사라지는건 아니고, 그당시의 사건(파일)만 삭제

git에서 기록이 손실되는 것을 방지함

커밋 삭제는 가장 최근의 커밋만 삭제할 수 있음

## git reset

특정 commit으로 되돌아가는 작업

특정 commit으로 되돌아가면, 되돌아간 이후의 commit은 모두 삭제됨

깃허브가 아닌 로컬에서의 commit 수정 기능. push 이후에는 사용하지 말 것

- git reset [옵션] <commit id>
    
    [옵션] 
    
    --soft 삭제된 commit의 staging area에 남김
    
    --mixed 삭제된 commit의 기록을 working directory에 남김(기본값)
    
    --hard 삭제된 commit의 기록을 남기지 않음
    

untracked.txt : commit에 포함된 적 없는 파일

이미 삭제한 commit으로 돌아가기

- git reflog
    - HEAD가 이전에 가리켰던 모든 commit을 보여줌
    - hart 옵션으로 지워졌던 commit도 reflog로 조회하여 복구 가능

## git restore

Modified 상태의 파일 되돌리기

Working Directory에서 파일을 수정한 뒤, 파일의 수정 사항을 취소하고, 원래 모습대로 되돌리는 작업

- git restore 파일명
    - 수정 전으로 되돌릴 수 있음
    - 원래 파일로 덮어쓰는 원리이므로, 수정한 내용은 전부 사라짐
