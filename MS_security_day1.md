# 📅 2025.06.23 Study Log

서울기술교육센터 📅 2025.06.27 Study Log

서울기술교육센터
**반도체**나 AI가르쳐요

Auzre 
금요일은 12시~13시

day1. 서버, 가상머신,LInux
day2. 네트워크
day3. Auzre - sk infosec. 엔지니어
day4. SIEM
day5. SIEM - toss security. 엔지니어

CIA = 정보보안의 목적.
Malware = 피해를 주는 목적인 프로그램
APT 공격
DDOS -> 선거철에 많이 쓰인대요 왜?
 (좀비피시로 공격함)
Ransomware => 몸값(데이터값) 내놔/돈 보내고 먹튀도함. 주로 비트코인을 보내달라함. (yes24)
피싱 📅 YYYY.MM.DD Study Log

서울기술교육센터 📅 YYYY.MM.DD Study Log

서울기술교육센터
**반도체**나 AI가르쳐요

Auzre 
금요일은 12시~13시

day1. 서버, 가상머신,LInux
day2. 네트워크
day3. Auzre - sk infosec. 엔지니어
day4. SIEM, Wazuh
day5. SIEM - toss security. 엔지니어

CIA = 정보보안의 목적.

- Malware = 피해를 주는 목적인 프로그램
- APT 공격
- DDOS -> 선거철에 많이 쓰인대요 왜? (좀비피시로 공격함)
- Ransomware => 몸값(데이터값) 내놔/돈 보내고 먹튀도함. 주로 비트코인을 보내달라함. (yes24)
- 피싱

정보유출방지 (usb,카카오톡 등)
비번 바꾸라하는 이유 brute force 
보안 솔루션(firewall, **IDS/IPS**)

시큐아이(firewall), 윈스(IPS)
V3, **suricata(open source IDS/IPS)**

**SIEM** 보안 정보와 이벤트 매니저
wazuh(4일차)

***Auzre로 SIEM 시스템을 구축하고 운영한다***
4일차 때, 개인 노트북 가상. 괜찮으면 클라우드로.

---

# Linux(UNIX)
## 특징
- 오픈 소스 -> 다양한 배포판, 확장성, 커스터마이징
- **다중 사용자**
- ***꽁짜다!!!***
- 이식성, 호환성?

MS windows 서버는 돈 내지만 기술지원가능.
But, Linux는 무료이나 기술지원X.

오 안드로이드도 리눅스 기반임.

실습 리눅스 Rocky Linux.
기업들도 리눅스로 확장하고 있음. 무료라서! (+ MS windows가 가격을 올리고 있어서)

서버 구축하고 싶으면 VMware 위에 올려서 가능!
이따가 이것저것 공부하는 법 물어볼까요? 
음, 리눅스 서버 구축 책 추천이나... 뭐 없나?
버그바운티에 참여하고 싶은데 공부하셨던 방법이나 책 있나요?

리눅스는 거의 다 CLI로 쓴다.

리눅스 파일 구조, 디렉터리 계층구조, **symbolic link, hard link**
Windows? ==> 대소문자 구분X
***but, Linux? ==> 대소문자 구분O***

---

# Directory
root => 신(ID). / ==> root Directory
etc => 환경설정/응용프로그램.
bin => command(손상되면 커널이 명령을 내릴 수 없다?)

- pwd(print working directory)
- cd(change directory) cd / => 절대경로, cd [디렉터리명] => 상대경로
- ls(list segment) -l:상세정보 / -a:숨긴 파일 / -i:
- mkdir(make directory)
- ==> 동시에 여러개 만드는법? 띄어쓰고 입력.
- ==> -p는 연속적인 하위 디렉터리 계층 생성가능.
- ~~rmdir(remove directory)~~ 이건 빈 디렉터리일 때 지울 수 있음. 아니면 불가능하기에 잘 안씀.
- rm(remove)
- ==> rm이 편함. 디렉터리 지울 때, 그 해당 디렉터리가 비어있다? -d: directory 디렉터리 제거.(근데 비어있을 때만 적용되어서 얘도 잘 안씀. 주로 -r 사용!) 
- ==> 하지만 비어있고 안에 많은 파일이 있으면 -r: Recrusive 재귀적으로 제거.
- ==> 이러면 다 물어보니까 귀찮자나, -f: Force로 강제로 제거.
- 번외) rm -rf /* => 루트 아래 모든 폴더 제거. (이거 치면 다 날라갑니다)


# file
- touch ==> 임시 파일 생성 시에 사용.
- cat(concatenate)
- more ==> 스페이스바로 내리고, q로 종료. 다시위로 올리는 것은 불가능.
- **less ==> 화살표 키로 스크롤 가능!! q로 종료. 양방향으로 스크롤 가능함. 훨씬 유용**
- **tail ==> 실시간 갱신되는 옵션 -f로 씀.** 수시로 변경되는 내용을 많이 사용.


## copy,  move
- cp(copy)
- ==> 디렉터리를 복사할 때, -r: Recrusive 재귀적으로 폴더 내부의 파일까지 모두 복사.
- mv(move) ==> 이동인데, 실제로는 복사하고 기존 파일을 제거함.
- ==> 파일명을 바꿀 때도 주로 쓰임.


## grep
- ==> 문자열을 찾음
- ==> 주로 **파이프라인(|)** 와 함께 사용함. 리눅스 배우고 이거 안쓰면 간첩임.
---

썰1) 이란 핵시설 공격 스턱스넷(Stuxnet, 악성코드)</br>
==> 인터넷이 접근이 안되는데...?</br>
**인터넷이 없는데도 어떻게든 악성코드를 심는다**</br>

썰2) 3.20 사이버테러, (농협/신한), (ytn/mbc)의 pc들을 한번에 다 먹통. 재부팅하면 mbr이 뜸(부팅파일이 없어짐)</br>
==> 어떻게 한번에...? (보안 솔루션, 즉 중앙에서 감시하는 솔루션이 해킹을 당했고, 역으로 악성코드를 퍼뜨림.)</br> 
**보안 솔루션은 양날의 검이다**

==> 보안 엔지니어는 밤샐 준비를 해라... 
OT 기업 보안

---

# 리눅스 파일 구성

리눅스 파일 = [Filename] + **inode** + [Data]
inode는 파일 정보가 담긴 구조체!! => 파일의 주민등록증 역할.
==> 파일의 종류|크기|소유자, 파일 변경시간, 파일명 등등 파일의 상세정보와 [Data] 주소(index)가 담김.




---

# ⭐ 문서 편집(vi)
## vi(visual editor)
- ==> 명령모드에서 i(insert)로 입력모드로 전환. esc로 복귀.
- h/j/k/l ==> 방향키가 없을 때 입력모드에서 (좌/하/상/우) 이동 가능!! (서버실에서 꽤나 유용하다)
- r(replace) 명령모드에서 커서에 있는 문자하나를 교체! r + [교체할 문자]
- **u(undo) 명령취소** / **U 해당 행에서 한 모든 명령 취소!!** / **:e! 마지막 저장으로 돌아가기(작업 모두 취소)**
- cw, #cw(change word) 커서 위치부터 현재 단어 끝까지 수정. 3cw는 커서 3개의 단어! (즉 공백이 3번 나올 때까지 모두 지움)
- G(마지막 행으로 커서 이동)/ [행번호] + G (지정된 행번호로 이동)
- cc(change column) 현재 행의 모든 내용 수정.
- **:set nu ==> 줄 번호 보이기!**
- yy, #yy(행 복사하기) 행의 내용을 오려두기.
- dd, #dd(행 잘라내기) 행의 내용을 잘라내기.
- P,p (위,아래)에 붙여넣기.
- **/[찾고자 하는 문자열] ==> 검색하기. n은 다음 문자열, N은 이전 문자열.**
- :%s/[바꾸고자 하는 문자열]/[바꿀 문자열] ==> 문서 내의 모든 바꾸고자 하는 문자열을 바꿀 때 사용.
- ==>[시작행],[끝행]s/[문자열1]/[문자열2]/gc ==> gc 옵션은 g 각 항목의 모든 문자, c는 confirm 하나씩 확인하며 변경!

- nano,pico,emacs도 있어용 근데 어려움

리눅스는 환경설정을 다 vi로 할 수 있음. ex. ssh_config

![image](https://github.com/user-attachments/assets/53c12321-74e0-4846-865a-ccaf7afd95a0)
![image](https://github.com/user-attachments/assets/d9233399-45b1-4ac3-97aa-02d913633ef8)
![image](https://github.com/user-attachments/assets/a4bd9084-0d53-4858-a40f-0bf0a2e9185d)
![image](https://github.com/user-attachments/assets/7cf7507a-c949-438c-b242-f253bf0e75ef)
![image](https://github.com/user-attachments/assets/188d939f-904a-4af9-b14f-98ed66dda061)

---

# Process(프로세스)

***Parents process*** 
- 부모가 없어지면 자식도 없어짐. ㅠ
***Deamon***
***Orphan process***
- 고아 프로세스, 부모가 없어지는데 자식이 안없어지고 비정상적으로 남아있음.
***Zombie process***
- 아무것도 안하는 프로세스. 이녀석으로 성능 저하를 유발하기도 함.

## ps(process)
- **ps -ef** 이거 모르면 리눅스 하지마.
- -f: 프로세스 상세정보
- -e: 전체 프로세스 목록 출력
- ==> 보통 grep이랑 같이 사용함.
  
- ~~pgrep~~ => ps | grep

- **kill(프로세스 종료)**
- kill [-시그널] PID
- **-2: 중단**(인터럽트), **-9:죽이기**(프로세스 강제 종료), **-15: 종료**(프로세스 관련 파일 정리 및 종료, 종료되지 않을 수도 있음)
- =>  종료된 프로세스를 다시 살리는 것은 일반적으로 불가능!
- history로 확인해서 뭔짓을 했는지 확인하는 방법은 있다~
- => tty를 치면 내 터미널이 몇번째 터미널인지 알 수 있음(ex. /pts/0) 최대 6개까지 가능 그 이후론 gui로.
- [명령어] > /dev/pts/[명령어를 실행할 터미널] (내 터미널에서 다른 터미널로 명령어 실행이 가능함. 꿀잼)

- **top**
- 실행중인 프로세스의 정보를 주기적으로 확인.
- => 메모리를 얼마나 쓰는지, cpu사용량은 어떻게 되는지 실시간으로 확인.

---

# 사용자 관리
- /etc/passwd ==> 비밀번호 같지만 사용자 계정 정보가 저장된 기본 파일임.
- ==>> 비번은 /etc/shadow에 암호화 되어 저장.
- **1000~ 부터 일반 사용자에게 id를 줌** / 500~은 시스템 id?
- shadow의 $(달러)는 암호화가 설정되었음을 의미함.

## useradd(user 계정 생성)
- useradd [옵션] [로그인 ID]
- passwd [로그인 ID] ==> 패스워드 변경.(루트라서 가능해요)
![image](https://github.com/user-attachments/assets/6ec9bdcf-2a79-4898-ba38-d51d20f8ea54)
 
소프트웨어 설치 숙제. 3개!
util/
1. cisco packet tracer
2. mobaXterm_Installer_v25.2
3. sublime_text_build_4200_x64_setup
4. WinSCP-6.5.1-Setup
- 다 무료니까 free or trail 버전으로만 설치합시다!!! 
## 📌 오늘 배운 개념 요약



- 
- 
- 

---

## ✅ 

1. 
2. 
3. 
4.

---

## 🧠 오늘의 느낀 점 ☑️

-
- 
- 

---

## ❓ 오늘의 궁금한 점 🔍

-
- 
- 

---

## 🔖 내일 목표 🎯

- 
- 
-

