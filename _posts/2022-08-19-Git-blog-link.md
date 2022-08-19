---
layout: post
title: 깃허브 블로그 생성하기, jekyll 테마 적용 / Create Git-hub Blog, Adapting jekyll theme
date: 2022-08-19 14:18 +0800
last_modified_at: 2022-08-19 14:18:25 +0800
tags: [Blog, Git, Git-hub, jekyll theme, jekyll]
toc:  true
---

---

안녕하세요. **조기개발** 입니다.   
블로그 첫 포스팅은 깃허브 블로그 생성하는 방법 및 jekyll 테마 적용하는 방법에 대해 포스팅 해보도록 하겠습니다.

---

## 0. 환경

저는 윈도우 10 운영체제를 사용하고 있으며   
Visual Studio Code를 사용하여 포스팅 중입니다.
추가적으로 Ruby와 Git 설치가 필요합니다.

Ruby 설치 링크   
[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)  

Ruby 설치 완료 후 Ruby cmd를 실행시켜   
(윈도우 키 + Ruby 타이핑)   
아래와 같은 명령어를 실행시켜 줍니다.   

>gem install jekyll   
>gem install minima   
>gem install bundler   
>gem install jekyll-feed   
>gem install tzinfo-data   

설치 후 jekyll 테마 버전 확인

>jekyll -v

---

## 1. 테마 고르기

먼저, 적용하고 싶은 테마를 jekyll theme 사이트에서 고른 후   
자신의 Git-hub에 fork 합니다.   

![img](/_data/0819_2.JPG)

**우측 상단 fork 진행**

[http://jekyllthemes.org](http://jekyllthemes.org/)   

테마 다운로드 후 압축 해제, repository에 붙여넣는 방법도 괜찮습니다.   

---

## 2. Git-hub repository 이름 설정 및 블로그 주소

**<깃허브 아이디>.github.io** 의 형식으로 repository 이름을 설정합니다.

![img](/_data/0819.JPG)

그렇다면 https://chogiseong.github.io/ 와 같은 주소로
블로그 링크를 생성할 수 있습니다.

---

## 3. Git 설치

하기 링크를 통해 Git 설치 후 Git Bash를 실행합니다.

[https://git-scm.com/download/win](https://git-scm.com/download/win)

![img](/_data/0819_3.JPG)

Git에 저장되어있는 블로그 repository를 원하는 로컬 repository에 Clone 합니다.   

---

## 4. 로컬 블로그 실행 및 _config.yml 수정, 반영

로컬로 받은 블로그 repository 경로로 이동 후

>gem install tzinfo   
>gem install tzinfo-data   
>bundle install   
>bundle update   
>bundle install   

설치 확인 후   

>bundle exec jekyll s

64bit 운영체제일 시 tzinfo 관련 에러가 발생할텐데   
**버전 확인 후 맞춰주고, GemFile 수정이 필요합니다.**  

>vi Gemfile

내용 추가

>gem "tzinfo"   
>gem "tzinfo-data"  

실행되는 것까지 확인이 되었다면   
http://127.0.0.1:4000 로 접속 후   
commit 전 preview를 볼 수 있습니다.

![img](/_data/0819_4.JPG)

_config.yml 파일은 블로그 테마의 환경설정 파일이기 때문에
기본적인 정보 (블로그 title, description)등을 수정해야 합니다.

---

## 5. Git-hub 에 수정사항 반영

수정 후 하기 과정을 통해 Git에 commit할 수 있으며
>git add .   
>git commit -m "commit 내용"   
>git push origin master   

>git status   
>git diff   

등의 커맨드로 변경점 확인을 할 수 있습니다.

---

감사합니다.
