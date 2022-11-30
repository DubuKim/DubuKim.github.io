# 프로젝트 Build 과정


## 사전 설치

프로젝트를 시작하기 전, 아래와 같이 github blog를 위한 프로그램을 설치 과정을 진행했다.

- 노트북의 OS가 window이기 때문에, Git에 접근하기 위한 Git bash 설치 후 Token으로 로그인
- Ruby 설치


## Jekyll의 기본 활용

Github page의 기초를 만들기 위해, Git에 미리 만들어놨던 repository를 clone하였다.

repository에 Jekyll을 설치하였고, Git 원격 repository에 Push하기 전, 

``` jekyll serve``` 명령어를 통해 local에서 잘 작동하는지 확인하였다. 

이후 _config.yml을 간단하게 수정하여 dummy data를 내 정보로 교체하였고,  

_post directory에 Post Upload를 테스트하기 위한 게시글을 작성 한 뒤, Git에 Push했다.

## Theme 변경

#####  Trouble 1

Jekyll의 Theme을 변경하기 위해 "https://jekyllthemes.io" 사이트에서 검색을 하다가 

https://github.com/CloudCannon/hydra-jekyll-template

해당 템플릿으로 결정을 한 뒤, 상위 directory에 clone을 하고 _post directory를 제외한 나머지 파일들을 붙여넣었다.

하지만 Push를 하려고 시도를 했을 때 error가 발생했었고, 확인을 해보니 theme를 clone하여 

remote repository가 나의 repository가 아니라, hydra의 repositoy로 되어있었다.

따라서

``` 

git remote remove origin

git remote add origin <원격 repository>

```

와 같은 명령어를 통해 remote reposity를 변경하고, PUSH를 했다.


#####  Trouble 2

hydra theme를 적용한 뒤, blog의 기본 정보를 수정하려고 하였으나 원활하게 진행이 되지 않았다.

결국 hydra theme 대신 강사님이 사용하신 Lanyon 테마를 github에서 zip으로 다운받은 뒤, 적용을 시키고 PUSH를 했다.

하지만 깜빡하고 미리 serve로 확인을 하지 않았기에, hydra theme가 여전히 적용이 되어있었다.

git에는 이미 섞여있는 theme가 적용 되어있었기에 remote 저장소를 덮어씌우는 방법을 택하였다.


``` 

# local의 .git directory 삭제
rm -rf ./.git

# local에 새로운 git 생성
git init

# 다시 git remote 연결 
git remote add origin <원격 repository>

# add 및 commit 후 강제로 덮어씌우기
git push --force --set-upstream origin main


```

## Theme 수정

이후 내 블로그로 사용하기 위해 기존 data를 수정했다.

- Blog에 내 정보를 넣기 위해 _config.yml을 편집했따..
- sidebar에 있는 page를 정리하기 위해 sidebar.html에 home 태그를 제외하곤 주석처리를 했다.
- sidebar가 page의 시작할 때 떠있기 위해, input tag의 마지막에 checked를 추가했다.
```
<input type="checkbox" class="sidebar-checkbox" id="sidebar-checkbox" checked>
```
- theme의 색을 바꾸기 위해 default.html의 body element에 class를 추가했다.
```
<body class="theme-base-0d">
  ...
</body>
```

