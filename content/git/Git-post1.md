+++
title = "GIT 개요와 사용법"
date = "2023-05-28T21:29:20+02:00"
tags = ["golang", "programming", "theme", "hugo"]
categories = ["GIT"]
banner = "https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/1200px-Git-logo.svg.png"
authors = ["조영서"]
+++


-----
# GIT 개요

* 분산 버전 관리 시스템
* 2005년 리누스 토발즈가 개발
* 라이선스: GPL V2.0
* 개발배경
   * 2002년부터 리눅스 버전 관리시스템으로 BitKeeper(BitMover사의 상용 SW, 2016년 오픈소스, 개발 중단) 사용
   * BitMover사가 리눅스 개발자들이 무료로 사용할 수 있도록 하였으나, 앤드루 트리젤이 비슷한 소스 풀러를 만들면서 리눅스 개발자들에 대한 무료 사용을 철회
   * 리누스 토발즈가 다른 오픈소스 버전관리 시스템을 사용하려 하였으나 당시 원하는 기능을 만족하는 SW가 없어서 직접 만들게 됨
   * 그 후 리눅스 버전 관리 시스템으로 사용되면 현재 가장 많이 사용되는 버전 관리 시스템이 됨


# GIT 목표

* 빠른 속도
* 단순한 구조
* 비선형적 개발(동시 다발적 브랜치)
* 완벽한 분산
* Linux 커널 같은 대형 프로젝트에서 유용    


# GIT CLI

### GIT을 사용하는 방법
* git CLI
* 다양한 GUI 지원 SW 존재
* git의 모든 기능을 지원하는 SW는 git CLI

### GIT 설치
* 리눅스에는 기본적으로 설치되어 있음
* 없을 경우 sudo apt install git

### 작업 디렉토리 생성
* ex) mkdir -p ~/projects/w11/git-ex

### git 저장소 생성
* git init : 작업 디렉토리 git 저장소로 초기화
* git branch : 브랜치 보기, 기본 브랜치는 main

### git 업그레이드
* sudo add-apt-repository ppa:git-core/ppa -y
* sudo apt update
* sudo apt install git -y

### git 저장소 재생성
* git 저장소 삭제 & 디렉토리 삭제
* git init 실행
* 브랜치 확인


# GIT CLI 사용법

### 소스 관리 
* 관리 대상 여부
   * tracked(추적대상) : 관리 대상
   * untracked(추적대상 X) : 관리 대상 X
   * git status 로 확인

* 관리 대상 상태
   * committed : 버전관리에 안전하게 저장됨, snapshot
   * staged : 커밋할 대상이라고 표시된 상태
   * modified : 파일이 수정되었지만 staged 되지 않음
   * tracked인 파일은 변경을 감지함
   * untracked인 파일은 변경을 감지하지 않음
   * untracked인 파일이 새로 생긴 것은 감지함

* 관리 대상으로 변경
   * git add <file or 디렉토리>
      * untracked 파일을 tracked로 변경
      * 동시에 staged로 변경
      * 디렉토리를 지정한 경우 하위 모든 파일 변경

* Commit
   * git commit
      * staged 상태인 파일만 커밋 가능
   * 커밋 메시지 입력 필요

* 비교
   * git diff

* 커밋 히스토리
   * git log
      * 커밋한 이력 보여줌(최근 커밋이 제일 위)
   * git log --patch
      * 비교 결과
      * git log --patch -2는 최근 2개의 커밋만 비교

* 파일 삭제
   * git rm
      * tracked 상태의 파일 삭제
      * 커밋 필요

* 파일 이름 변경
   * git mv file_from file_to

* 되돌리기
   * 버전 관리 시스템이므로 과거의 스냅샷으로 되돌릴 수
   있음, 즉 잘 못 수정된 것을 얼마든지 되돌릴 수 있음
   * 하지만 잘 못 되돌린 것은 다시 되돌릴 수 없으므로
   되돌리는 작업은 각별한 주의를 요함

* 완료한 커밋 수정
   * git commit --amend : 커밋 재작성
   * 수정을 한 후 하나의 커밋으로 기록됨

* 파일 상태를 unstage로 변경
   * git reset HEAD <파일>

* Modified 파일을 되돌리기
   * git checkout -- <file>
   * 수정한 내용이 모두 사라지므로 주의 해서 사용
   * 브랜치를 사용해야 함

* 이전 커밋으로 되돌리기
   * 마지막 커밋을 취소
      * git revert <되돌리고 싶은 커밋 이름>
   * 특정 커밋으로 이동
      * git reset --hard <이동하려는 이전 커밋 이름>
   * 협업을 할 경우 되돌리기를 주의해야 하며, 자신만의
   브랜치를 만들어서 하는 것이 좋음

* branch
   * 코드를 통째로 복사해서 독립적으로 개발
   * 새로운 작업은 브랜치를 만들어서 하고 완성되면 합병
   * 어떻게 브랜치를 만들고 합병할 지 전략 필요
   
* branch 명령
   * git branch : 브랜치 보기
   * git branch <새 브랜치 이름> : 브랜치 만들기
   * git checkout <브랜치 이름> : 브랜치 이동
   * git checkout -b <새 브랜치 이름> 
   : 브랜치를 만들고 이동
   * git merge : 브랜치 합병
   * git log --oneline --decorate --graph --all
   : 로그에 브랜치가 잘 나타나게 표시
   * git branch -d <브랜치 이름> : 브랜치 삭제
