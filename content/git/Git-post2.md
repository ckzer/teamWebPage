+++
title = "GITHUB"
date = "2023-05-28T21:29:20+02:00"
tags = ["golang", "programming", "theme", "hugo"]
categories = ["GIT"]
banner = "https://alyssonmach.github.io/Minicurso-Git-e-GitHub/img/5.png"
authors = ["조영서"]
+++


-----
# GITHUB

* git을 기반으로 한 원격 저장소 호스팅 서비스
* 계정을 만들고 사용
* 라이선스: GPL V2.0   
* "2FA"(투팩터 인증)을 설정
* ssh key 생성과 계정에 추가


# 보안 설정과 ssh키 저장

* "2FA"(투팩터 인증)을 설정
* SSH key 추가
   * WSL에서 키를 생성한 후 공개키를 복사하여 github에 등록


# 저장소 만들기 & clone

* github에서 repository 생성
* 원격 저장소 clone
   * clone URL 복사
   * WSL에서 작업
      * cd ~/projects
      * git clone <URL>


# markdown

### 목록
#### 번호 있는 목록 : 내림차순 정렬
1. 첫번째
3. 세번째
2. 두번째

#### 번호 없는 목록 : *, -, +
* 첫번째
- 세번째
+ 두번째
-----
* 빨강
 * 녹색
  * 파랑

### 강조
*single asterisks*    
_single underscores_    
**double asterisks**     
__double underscores__     
~~cancelline~~


# 소스 저장소로 push
* github에서 clone한 소스를 커밋한 후 원격 저장소로 push
   * cd ~/projects
   * git add . : 모든 파일들 stage로 보내기
   * git commit -m "메세지 내용"
   * git push


# GITHUB PAGES
* GitHub의 Web Page Hosting
   * GitHub에서는 Web Page Hosting Service 제공
   * 정적인 Hosting
      * HTML, CSS, JavaScript 파일 서비스 기능
      * 서버 사이드 동적 호스팅 불가
* GitHub Pages는 2가지 페이지 서비스 제공
   * Project Pages Hosting
      * 각 프로젝트(저장소) 별 페이지 호스팅
   * User Page Hosting
      * 각 사용자 계정 당 하나의 페이지 호스팅
* Project Page 만들기
   * 저장소의 "Settings" 메뉴에서 "Pages"에서 "Branch"에서
   설정
   * https://<username>.github.io/<저장소이름>으로
   publishing 됨
* GitHub Pages URL
   * /index.html 파일은 https://사용자이름.github.io/저장소이름/
   * /aaa/index.html 파일은 https://사용자이름.github.io/저장소이름/aaa
   * /bbb.html 파일은 https://사용자이름.github.io/저장소이름/bbb
   * 저장소 URL : https://github.com/사용자이름/디렉토리
   * Web Page URL : https://사용자이름.github.io/디렉토리
   * **git push 후에 즉시 반영되지 않음**
* GitHub Pages 제한 사항
   * 상업적 사이트 금지
   * 거래에 대한 위험성 주의
   * 사용 제한
      * GitHub Pages 소스 저장소의 권장 제한은 1GB 
      * 게시 된 GitHub 페이지 사이트는 1GB를 초과 할 수 없음
      * GitHub 페이지 사이트의 대역폭 제한은 한 달에 100GB
      * GitHub 페이지 사이트의 builds 제한은 시간당 10회 


# 브랜치 전략

### 브랜치 활용
* 개발 작업은 main 브랜치에서 하지 않음
* 여러 명이 함께 개발을 할 때 각자의 브랜치를 만들어서 개발을 하고 메인 브랜치는 함부로 수정하지 않는 것이 좋음
* 혼자 개발할 때에도 소프트웨어가 배포되거나 퍼블리싱이 된 후에는 메인 브랜치를 함부로 수정하지 않는 것이 좋음
* 브랜치를 만들어서 소프트웨어를 개발하고 업데이트할 때 적절한 규칙을 정해서 사용하는 것이 브랜치 전략

* Git Flow
   * 패키지 소프트웨어 개발을 위해 고안된 전략
   * 웹서비스와 같이 명시적 버전 관리가 필요없이 수시로 업데이트되는 소프트웨어 개발에는 적합치 않음
   * 복잡함
* GitHub Flow
   * 웹서비스와 같이 명시적 버전 관리가 중요하지 않으며 수시로 업데이트 되는 소프트웨어 개발을 위해 고안됨
   * 브랜치를 단순하게 만들어 사용

### GitHub Flow
* Main branch
* 항상 Stable한 상태여야 함
* 모든 커밋은 언제 배포하든 문제 없어야 하고, 언제든 브랜치를 새로 만들어도 문제가 없어야 함
* Main 브랜치의 모든 커밋은 빌드가 되고, 테스트를 통과해야 함
* Topic branch
* 새로운 기능을 개발할 때에는 Topic 브랜치를 Main 브랜치로부터 생성함
* 별도로 Hotfix 브랜치를 관리하지 않으며, 버그 수정도 Topic 브랜치에서 진행함
* Topic 브랜치의 이름은 기능을 설명하는 명확한 이름으로 네이밍 해야 한다. 예를 들면, user-content-cachekey,
submodules-init-task, redis2-transition 등이 있음
* Topic 브랜치의 커밋은 기능이 완성되지 않았더라도 꾸준히 Push 함 (소스 백업의 기능)

### 새 브랜치 만들기
* 로컬과 원격(GitHub)에 브랜치 만드는 방법
1. 원격에서 만들고 로컬로 가져오기
   * GitHub에서 브랜치 만들기
   * git fetch -p
   * git checkout <브랜치 이름>
2. 로컬에서 만들고 원격으로 push
   * git branch <브랜치 이름>
   * git checkout <브랜치 이름>
   * 또는 git checkout -b <브랜치 이름>
   * git push <원격> <브랜치 이름>

### 코드 수정
* 새로 만든 브랜치에서 코드 수정
* 수정 내용 확인
* 수정 내용 GitHub에 업데이트
* git add
* git commit
* git push

### Pull Request(PR, 끌어오기 요청)
* GitHub에서 PR(Pull Request)
* 내가 수정한 내용이 있는 브랜치를 협업자들이 가져가서(pull) 검증할 것을 요청
* PR을 보며 협업자들이 코드를 검토하고 충돌사항(conflict)이 있는지 확인하고 충돌이 있으면 해결
* 혼자 개발할 경우 꼭 필요한 것은 아니나 검증 작업과 검증을 진행한 기록을 위해서 사용할 수도 있음

### 브랜치 병합(Merge Branch)
* PR를 요청받은 브랜치가 충돌이 없고 새로 적용하는데 문제가 없다고 결정되면 main 브랜치와 병합
* Pull Request UI에서 충돌이 없는 것으로 확인이 되면 병합(Merge)할 수 있음
* GitHub에서 병합한 후 로컬의 main에서 pull하여 원격(GitHub)의 main과 로컬의 main이 같도록 해야 함

### 브랜치 병합(Merge Branch) 후 삭제
* 병합이 완료된 후 브랜치는 더 이상 필요가 없으므로 삭제
* 원격(GitHub)의 브랜치는 UI에서 삭제 가능(휴지통 아이콘)(git push origin --delete <원격 브랜치 이름>)
* 로컬의 브랜치는 CLI로 삭제