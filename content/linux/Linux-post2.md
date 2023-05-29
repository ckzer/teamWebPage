+++
title = "Linux 사용법"
date = "2023-05-22T18:26:23+09:00"
tags = ["Linux", "shell script","OS"]
categories = ["Linux"]
banner = "img/banners/Linux/Linux_banner-2.png"
authors = ["김민수"]
+++

## Linux shell

**OS shell**
* 운영 체제 상에서 다양한 운영 체제 기능과 서비스를 구현하는 인터페이스를 제공하는 프로그램
* 셸은 일반적으로 명령 줄과 그래픽 형의 두 종류로 분류
* CLI(명령줄 인터페이스)
* GUI(그래픽 사용자 인터페이스)

**Unix 계열 CLI**
* 본셸 : sh
* 배시 : bash
* z셸 : zsh
* CLI(명령줄 인터페이스)
* GUI(그래픽 사용자 인터페이스)

**Windows CLI**
* 도스 프롬프트 :command.com(과거 윈도우)
* 명령 프롬프트 : cmd.exe
* 파워셸 : powershell.exe

**Linux용 GUI**
Linux는 GUI는 독립적으로 설치하여 사용
* GNOME
* KDE

## Linux 사용자와 권한

**Linux 사용자 계정**
* Linux 사용자는 계정을 가지고 로그인을 해서 사용
* 사용자 계정으로 로그인하기 위해서는 비밀번호(password)로 인증을 받아야 함
* 모든 계정은 숫자로 된 UID 값을 가짐
* root user : 모든 권한을 가짐(super user), root user는 UID 0번을 가짐
* 일반 user : root user가 아닌 모든 사용자 계정
* 모든 사용자는 자신의 home directory를 가짐
* 사용자 계정은 /etc/passwd 파일에서 관리됨
* 사용자 계정에 대하여 로그인을 허용할 수도 있고 금지할 수 있음
* 보안 문제로 root 계정은 로그인을 금지시키는 추세임

**Linux 사용자 그룹**
* 모든 사용자 계정은 하나 이상의 사용자 그룹에 속함
* 사용자 그룹은 숫자로 된 GID 값을 가짐
* root user는 root group에 속함
* root group GID 0번을 가짐

**Linux 권한 관리**
* Linux에서 모든 자원은 파일(디렉토리 포함)로 관리됨
* 모든 파일에는 소유권(owner)이 지정됨
* 모든 파일에는 소유자와 소유자 그룹 그리고 다른 사용자에 대하여 권한을 설정할 수 있음
* 모든 파일에는 읽기/쓰기/실행 권한을 설정할 수 있음

**루트 권한의 사용**
* 보안 문제로 root사용자 계정을 사용할 수 없게 설정하는 경우가 많음(Ubuntu default)
* sudo 명령어 : 일반 사용자 계정이 root 권한으로 명령을 실행할 수 있음
* /etc/sudoers 파일에서 sudo 명령을 사용할 수 있는 사용자 계정 지정

**password 바꾸기 권한 필요**
* passwd [사용자 계정]

## Linux 기본 명령

**셸**
* 셸 확인 : ps
* 셸 변경 : 셸 프로그램 실행(sh, bash, zsh ; 설치되어 있어야 함)
* 셸 탈출 : exit

**파일 보기**
* 파일 목록 보기 : ls, ls -a, ls -l, ll(alias)
* . : 현재 디렉토리
* .. : 상위(부모) 디렉토리
* .으로 시작되는 파일 : 숨김 파일
* 파일 종류 : 파일, 디렉토리, 링크, 파이프

**파일 권한(파일 모드)**
* 9글자 : owser/group/other 3자씩
* 읽기/쓰기/실행 : rwx
* 2진수 값 : 허용(1), 금지(0)
  * rwx : 7
  * --- : 0

**자동 완성과 과거 명령 실행, 도움 보기**
* 명령 입력의 일부만 입력한 수 tab을 입력하여 자동 완성 기능 사용 가능(미리 설정)
* 위/아래 화살표를 이용하여 과거 실행한 명령을 실행
* 명령어 --help 또는 man 명령어

**디렉토리**
* 루트 디렉토리 : 모든 디렉토리의 출발점(/)
* 디렉토리 위치 : 절대 경로(루트 디렉토리 부터), 상대 경로(현재 디렉토리 부터)
* / : 루트 디렉토리
* ~ : 홈 디렉토리
* .. : 상위 디렉토리
* . : 현재 디렉토리
* • 이동 : cd (change directory), 읽기 권한이 없으면 이동할 수 없음
* cd <경로> : <경로>로 이동
* cd .. : 상위로 이동
* cd 또는 cd ~ : 홈 디렉도리로 이동
* cd - : 이전에 있던 디렉토리로 이동
* 확인 : pwd(print working directory)

**파일 속성 수정**
* chown : 파일(디렉토리)의 소유자 수정(chown uid:gid file_name)
* chmod : 파일(디렉토리)의 권한 수정(chmod 755 file_name, chmod o+x file_name)

**파일(디렉토리) 다루기**
* mkdir : 디렉토리 만들기
* rmdir : 디렉토리 지우기(빈 디렉토리만 지울 수 있음)
* cp : 복사 (-R 하위 디렉토리까지 복사)
* touch : 빈 파일을 만들기
* mv : 파일이나 디렉토리를 옮기거나 이름을 변경
* rm : 지우기 파일이나 디렉토리를 지울 수 있음(강력한 옵션 ; rm -rf <파일 또는 디렉토리 이름>)
* find : 파일 찾기 (find / -name 문자열)
* which : 경로에 있는 파일 찾기
* tree : 디렉토리를 트리모양으로 보기(별도 설치 필요, tree -L 3)

**텍스트 파일 보기**
* 텍스트 파일은 편집 프로그램을 이용하여 읽고 수정할 수 있음
* 텍스트 파일을 보는 명령어
* more
* cat
* head [-n 줄수]: 맨 앞의 10줄만 보기[ -n에 설정한 줄 수 만큼 보기 ]
* tail [-n 줄수]: 맨 뒤의 10줄만 보기 [ -n에 설정한 줄 수 만큼 보기 ]
* grep : 지정된 문자열이 포함된 행만 표시

**주요 디렉토리 및 파일**
* /etc : 시스템 환경 설정에 대한 파일들이 저장된 디렉토리
* /etc/passwd : 사용자 계정
* /etc/group : 사용자 그룹
* /etc/os-release : 배포판 버전 정보
* ~/.bashrc : bash 설정 파일
* /tmp : 임지 파일들을 저장하는 디렉토리
* /etc/apt/soruces.list : 패키지 저장소 목록을 저장

**파이프**
* |를 써서 앞의 명령 실행 결과를 뒤 명령의 입력으로 사용할 수 있다
* 예 ps -ef | grep abc

**프로세스 보기**
* ps : 프로세스를 보는 명령, 현재 셸의 실행 프로세스 표시
* ps -ef : 현재 시스템에서 실행 중인 모든 프로세스 목록 표시
* ps -ef | grep python : python 이란 문자열이 있는 프로세스 행 표시

**주요 시스템 명령**
* uname : os 정보 보기 (uname -a)
* cat /etc/os-release : 배포판 정보 보기
* id : 사용중인 계정에 대한 정보
* uptime : 실행된 시간
* last reboot : 부팅된 시간
* ip addr : ip 주소 보기

**환경 변수 보기**
* env : 환경 변수 보기

**패키지 관리(Ubuntu, Debian)**
* apt : 패키지 관리 명령(관리자 권한 필요)
* sudo apt update : 패키지 목록 업데이트
* sudo apt upgrade : 설치된 패키지(소프트웨어)들을 최신 버전으로 업그레이드
* sudo apt install <설치할 패키지 이름> : 패키지 설치

**시스템 자원 보기**
* df : 파일 시스템 보기(df -h)
* du : 디렉토리의 파일 크기 보기(du -sh *)
* top : 자원 사용 상위 프로세스 보기
* htop : 별도 설치 필요

**웹 관련 명령**
* curl : cli browser
* wget : 웹 다운로드