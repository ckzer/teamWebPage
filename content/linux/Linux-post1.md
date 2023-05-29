+++
title = "Linux 개요"
date = "2023-05-22T18:26:23+09:00"
tags = ["Linux", "shell script","OS"]
categories = ["Linux"]
banner = "img/banners/Linux/Linux_banner-1.webp"
authors = ["김민수"]
+++

## Linux 개요

Linux란 Linux Kernel 기반의 오픈 소스 Unix 계열 (Unix like) 운영체제들을 의미한다.
유닉스 계열 (Unix like) : 유닉스와 비슷하면서 유닉스가 아니다 는 뜻으로
유닉스 (UNIX) 와는 별개의 용어이다.

## OS 구성

운영체제 (OS; Operating System) 의 구성
* kernel
* Library
* Utilities
* User Interface

![OS구성](https://github.com/kmspeter/w4/assets/48709321/ad534715-ffe9-4a52-85a4-0974b5d9ecfa)

## OS Kernel

**OS Kernel**
운영체제의 핵심 , 하드웨어 자원을 관리하고 프로그램을 실행하게 함

**커널의기능**
커널은다음과 같은 4 가지 기능을 수행
* **메모리 관리:** 메모리가 어디에서 무엇을 저장하는 데 얼마나 사용되는지를 추적
* **프로세스 관리:** 어느 프로세스가 중앙 처리 장치(CPU)를 언제 얼마나 오랫동안 사용할지를 결정
* **장치 드라이버:** 하드웨어와 프로세스 사이에서 중재자/인터프리터의 역할을 수행
* **시스템 호출 및 보안:** 프로세스의 서비스 요청을 수신

![OS Kernel](https://github.com/kmspeter/w4/assets/48709321/456939e2-5c13-4849-b012-63fc5470bb25)

## Kernel 종류

**Single-tasking and multi-tasking**
* 싱글태스킹 : 한 번에 하나의 프로그램만 실행 가능
* 멀티태스킹 : 동시에 2개 이상의 프로그램을 실행 가능(time-sharing)

**Single- and multi-user**
* 단일사용자용(single-user) : 사용자 구별이 없음
* 다중사용자용(multi-user) : 사용자별 자원과 프로세스를 식별하여 여러 사용자들이 독립적으로 사용할 수 있도록 지원

**단일형커널과 마이크로커널**
* Monolithic Kernel : 모든 운영체제가 하나의 커널 공간에서 실행됨
    * 통합되어 한 번에 실행되므로 더 빠르게 실행
    * 모듈간 상호 작용이 직접 실행됨
    * 구조가 단순함
    * 전체 커널을 잘 만들어야 함
* Microkernel: 최소한의 운영체제 기능만을 커널에 구현하고 다른 기능들은 서버 형태로 제공
    * 작고 독립적이어서 모듈간 영향을 많이 주지 않음
    * 부분적으로 재 로드할 수 있고, 커널 전체를 재 컴파일 하지 않고 기능 추가 가능
    * 실행에 부가 비용이 발생 -> 성능 문제 발생 가능

## 단일형커널과 마이크로커널

![단일형커널과 마이크로커널 1](https://github.com/kmspeter/w4/assets/48709321/1512efa5-cc90-46f7-817e-3a7d9bb58d97)

![단일형커널과 마이크로커널 2](https://github.com/kmspeter/w4/assets/48709321/32923a20-32ae-40ea-be79-7043c3ddb195)

## 리눅스 커널맵

![리눅스 커널맵](https://github.com/kmspeter/w4/assets/48709321/5dd60ca0-01f7-4df1-a1d3-772c7852106e)

### Linux Kernel 분류

**Multi-tasking, Multi-user, 단일형커널**
* Linux kernel은 기본적으로 Multi-tasking, Multi-user, 단일형커널
* 임베디드 OS의 경우 커널을 수정하여 Single-task나 Single-user용으로 사용하기도 함

### Unix와 Linux의 역사

**유닉스(Unix)의 역사**

![Unix와 Linux의 역사 1](https://github.com/kmspeter/w4/assets/48709321/ba2b1526-9fc4-4927-a379-83ffd2249475)

**Linux 역사**

![Unix와 Linux의 역사 2](https://github.com/kmspeter/w4/assets/48709321/8ac5fdf9-5581-43a8-9af1-77009bf19cd9)

## Unix 계열

![Unix 계열](https://github.com/kmspeter/w4/assets/48709321/f5157833-887f-4935-82aa-d977be221068)

## Linux 배포판(Distro, Distribution)

* 리눅스 배포판(-配布版, Linux distribution, 간단히 distro)은 리눅스 커널, GNU 소프트웨어 및 여러 가지 자유 소프트웨어로 구성된 운영 체제
* 설치하고 사용하기 쉽게 배포용 패키지를 만들어서 제공
* GNU GPL을 따르는 리눅스 라이선스에 따라 소스 공개만하면 누구나 리눅스 배포판을 만들어 무료나 유료로 배포할 수 있음
* 리눅스 홈페이지(linux.org)에는 인기있는 24개의 배포판 목록이 있음
* 그 중 자주 보게 되는 배포판들은 다음과 같음
  * Ubuntu
  * Debian
  * Fedora
  * RedHat
  * CentOS
  * Rocky
  * SUSE
  * Arch

**Debian**
* Debian Project
* stable, testing, unstable
* 패키지 관리 : dpkg, apt, *.deb
* 안정적, 버전 업그레이드 느림

**Ubuntu**
* Canonical(영국 기업)
* LTS(Long Term Support), non-LTS
* 패키지 관리 : dpkg, apt, *.deb
* Debian을 기반으로 만듦
* 버전 업그레이드 빠름(최신 커널 지원)

**RedHat**
* IBM 인수
* RHEL(RedHat Enterprise Linux) : 기업용 운영체제(유료)
* 패키지 관리 : rpm, up2date, *.rpm

**Fedora**
* Fedora Project(RadHat 지원)
* RedHat의 커뮤니티 버전, 실험적, 테스트
* 버전 업그레이드 빠름

**CentOS**
* CentOS Project(RedHat 제휴)
* RedHat 완벽 호환 기업용 리눅스
* 2021 지원중단

**Rocky**
* The Rocky Enterprise Software Foundation
* CentOS 계승
* 패키지 관리 : rpm, yum, *.rpm

**SUSE**
* SUSE Software Solutions(독일 기업, EQT Partners)
* SLES(SUSE Linux Enterprise Server)
* 기업용으로 많이 사용됨
* 유럽에서 많이 사용됨

**openSUSE**
* openSUSE Project(SUSE 후원 받음)
* 패키지 관리 : ZYpp

**Arch Linux**
* Levente Polyak(Leader)
* latest stable versions of most software(major release없음)
* 최소한의 설치
* 패키지 관리 : pacman

**임베디드**
* Adroid
* ChromeOS
* 라즈베리파이용 OS : 라즈비안, SUSE, Ubuntu

**기업용 서버에 만이 사용되는 배포판**
* RedHat(RHEL), CentOS, Rocky Linux, SUSE(SOES), openSUSE

**데스크탑, 개인용, 딥러닝용 시스템에 만이 사용되는 배포판**
* Ubuntu, CentOS, Rocky Linux