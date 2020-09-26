## Initialize
```
git init
git remote add origin <URL>
	# git remote -v (로 확인 가능)
git config --global user.name <name>
git config --global user.email <email>
```
## Pull
```
git pull origin master
	# git pull == git fetch + git merge
```
## Push
```
 - optional
// git status //
// git diff <fileName> //

 - essential
git add .
git commit -m "message"
git push origin master
```
## git 해제 (.git 폴더 삭제)
```
rm -r .git
```
## 강제 pull
```
git fetch --all
git reset --hard origin/master
git pull -u origin +master
```
## 강제 push
```
git push -u origin +master
```
---------------------------
### branch 관리
```
git branch
  # 전체 branch 및 HEAD 가리키고 있는 branch 확인
git branch <branchName>
  # branch 생성
git checkout <branchName>
  # HEAD의 위치 변경
git checkout -b <branchName>
  # 생성과 동시에 HEAD 위치 변경  
git merge <branchName>
  # 현재 HEAD branch에 특정branch 병합
git branch -d <branchName>
  # 특정branch 삭제

rebase로 병합하기  
  git rebase <branchName>
    # HEAD branch를 <branchName> 뒤에 옮긴다. 실행 후 충돌은 직접 수정하고,
      git rebase --continue (취소하려면 --abort옵션 사용)
  git checkout <branchName>
    # <branchName>으로 HEAD를 변경
  git merge <last_HEAD branch>
    # 최종적인 내용은 merge 했을 때와 같지만, 이력이 다르다.
```
----------------------------
### tag 추가하기
```
git tag
git tag <tagName>
  # 현재 HEAD branch에 tag 추가
git tag -a <tagName>
  # tag에 주석 추가
git tag -am <tagName>
  # 한줄 주석 추가
git tag -n
  # 태그목록과 주석 모아보기
git tag -d <tagName>
  # 태그 삭제하기

```
----------------------

###  git status / git commit -a 시 한글 파일명 깨짐 현상
```
git config --global core.quotepath false
```

### git log시 한글이 깨짐 현상
```
git config --global i18n.commitEncoding utf-8
git config --global i18n.logOutputEncoding utf-8
```
----------------------------
### commit 수정

```
git log로 commit들의 해쉬값을 확인


git rebase -i <hash>	(원하는 commit 이전 기준으로)

수정모드로 들어가서(insert키) 원하는 commit에서 pick을 edit으로 수정,
(esc를 누른후 -> :wq! 입력 -> 빠져나오기)

git commit --amend
  # 수정모드 진행, 이후 위와 똑같이 빠져나오기


- commit 날짜 변경
  git commit --amend --no-edit --date "(날짜입력양식)"

	 ex) Tue Jul 7 18:33:43 2020 +0900
```
```터미널 내에서 복사/붙여넣기:  shift/ctrl + ins```
