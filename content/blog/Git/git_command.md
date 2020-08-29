---
title: git의 기본 용어와 명령어 정리
date: 2020-08-28 16:49:46
category: Git
draft: false
---

_요즘 들어 조금 친해진듯한 `Git`_

아직 모르는 명령어가 넘쳐나지만 일단 내가 익숙해진 명령어들과 `Gibhub`의 기능들을 정리해본다.

우선 Git의 기본 플로우는 `pull - add - commit - push`이다.

---

```html
git remote add 원격저장소이름 원격저장소url
```

원격저장소이름으로 원격저장소의 주소를 추가해준다. 이때 이름은 대부분 `origin`을 사용한다.  
<br>

```html
git fetch
```

`fetch`를 실행하면 원격저장소의 최신 내용을 확인할 수 있다. 이 때 최신 이력은 로컬에 이름없는 브랜치로 가져오게 된다.  
<br>

```html
git pull origin master
```

`pull`은 `fetch`와 비슷하지만 최신 커밋을 가져와서 로컬의 브랜치와 `merge`까지 해준다.  
<br>

```html
git init
```

현재 폴더에 `.git`이라는 하위 디렉토리를 만든다.  
<br>

```html
git branch
```

로컬의 브랜치를 확인할 수 있다.

> master가 가장 기본적인 브랜치다.

<br>

```html
git branch 브랜치이름
```

이 명령어로 새로운 브랜치를 생성할 수 있다.  
<br>

```html
git branch 브랜치이름 특정브랜치이름
```

특정브랜치(=특정시점)과 대조해서 브랜치를 생성할 수 있다.  
<br>

```html
git branch -d 브랜치이름
```

선택브랜치를 삭제할 수 있다.  
<br>

```html
git checkout 브랜치이름
```

브랜치를 전환하는 것을 `checkout`이라고 한다.  
<br>

```html
git merge 브랜치이름
```

현재 체크아웃되어있는 브랜치에 특정브랜치를 병합한다.  
<br>

```html
git status
```

현재 체크아웃되어있는 브랜치의 현 상황을 보여준다.  
<br>

```html
git add 파일명
```

선택파일을 커밋하기 전 스테이징 상태로 만들어준다.  
<br>

```html
git add *` or `git add .
```

이 명령어는 아직 의미가 많이 모호한데, 알아본 바로는 `add *`는 파일명이 '.'으로 시작하는 파일들을 제외한 모든 파일을 `add`하고, `add .`는 파일명이 '.'으로 시작하는 파일들도 모두 `add`한다.  
<br>

```html
git commit -m "커밋로그"
```

`git commit` 명령어만 입력하면 terminal창에 edit창이 뜨는데 커밋로그를 입력하고 `:x!`을 입력해 edit창을 종료해야한다. 이 번거로운 과정을 줄이기 위해 `-m`을 추가하면 간편하게 진행할 수 있다.  
<br>

```html
git commit -am "커밋로그"
```

`-am`을 추가하면 `add`를 `commit`과 동시에 할 수 있다.  
<br>

```html
git log
```

최신 커밋이력을 확인할 수 있다.  
<br>

```html
git reset 돌아가고싶은커밋
```

해당 커밋으로 돌아가고 그 사이에 있는 커밋이력은 삭제한다.  
<br>

```html
git revert HEAD~1
```

원격저장소에 `push`가 된 상태라면 `revert`를 사용해 되돌려야한다.  
<br>

```html
git push origin master
```

커밋한 내용들을 원격저장소에 `push`한다.  
<br>
