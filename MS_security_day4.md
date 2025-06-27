#Wazuh 서버 구축 및 실습.

# SIEM

# 서버의 구조
1. Agent ==> 보안 이벤트를 서버로 전송
2. Server ==> 서버는 그 이벤트를 수집하고 분석, 분류함.
3. Indexer ==> 서버 클러스터가 모은 정보들을 깔끔하게 정리함.
4. Dashboard ==> 인덱서가 보여주는 것을 시각화하여 보여줌.

## Agent
Agent가 없는 방식도 있음.
==> 별도의 프로그램 없이 서버와 통신. (ssh로 통신함)
호환성이 좋지 않은 녀석들은 Agentless를 택해서 로그를 숮집함.

## Server
서버는 에이전트로부터 전달받은 데이터를 디코딩 및 분석. 이벤트 처리
Filebeat으로 인덱서에게 전달.

## Indexer
인덱서는 분석된 데이터를 정리하고 검색할 수 있게 저장함.

## Dashboard
가공한 정보를 사용자에게 보여줌. 시각화해서 보여줌.

agent가 netstat에 붙을 때 1514 1515가 있어야 붙을 수 있다.

1. 와주 서버를킨다.
2. admin 계정을 찾는다.
3. netstat -ano 로 1514 1515가 열려있는지 확인(wazuh tcp/ip)
4. 방화벽 내리고
5. ping, telnet으로 열려있는지 확인하고
6. 접속하기
7. 로그인하기

리눅스는 크게 데비안, 레드햇으로 나뉨.

실제 서버나 회사에서는, 파일을 배포를 합니다. 
클릭해서 다운받으세요~!

여기다가 기능추가 실습.

# Sysmon
cs - iternal
filtering rule 추가. (토핑을 얹어준다) 
wazuh와 연동.
규칙 ex. cmd에서 ping을 치면 로그를 남겨줘!

sysmon에 정보가 쌓이면 이걸 wazuh agent가 server로 보내주는 역할임.
그니까 지금하는 보안 솔루션은.

1. 규칙에 따른 정보를 Agent가 수집한다
2. Agent로부터 온 정보들을 Server가 분류,분석한다.
3. Server가 indexer로 정보를 보내면 indexer는 그것을 정리한다.
4. Dashboard는 indexer의 정보를 관리자가 보기 쉽게 시각화해서 나타냄.

<CommandLine condition="contains">cmd.exe /c *http://*%AppData%</CommandLine> 악성코드에 주로 있어서 rule에 존재한다.
Sysmon에서 중요한 것들을 선별할때는, wazuh 서버 자체에서도 설정을 해줘야함.
wazuh가 건드릴 수 없으므로 rules를 chown으로 바꿔줌

**wazuh server랑 연결되는 취약점 CVE-2025-24016 재현해보자**
## chown(change owner)
- chown [사용자].[그룹] [파일명]

/var/ossec/bin에
./wazuh-control restart로 서버  재시작.

주로 threat hunting을 사용함. filter로 dashboard의 규칙별로 확인 가능. 
현실에는 인사DB가 저장되어  있다.

# 와주 삭제하는법.
- agent와 와주에 있는 정보도 삭제해야함.
수상한 로그가 발견되면 ip -> 누가 쳤는지 프로필이 뜸. ㄷㄷ
agent가 삭제되어도 기록은 남아있다. 대부분 상용화 제품들이 그렇게 해요.
==> 기록을 해야 나중에 일터지면 확인하지.

***중요한 것은 Agent는 Server를 바라봐야한다.***
그럼 패킷이 다 서버로 간다는 건데, 만약 중간에서 IP를 변조가 들어가서 중간에서 패킷을 가로챈다면?
아니면 Server를 공격자의 악성코드의 Agent로 만들어서, 받는 패킷을 모두 다시 공격자의 Server로 들어오게 만든다면?
근데 만약 내가 여기 학생들에게 내 아이피를 바라보는 agent를 설치하라하고, rules을 악의적으로 설정해서 중요한 정보가 들어오게 만든다면? 
이건 악성코드 아닌가?

또 중요한 건, Agent에 Sysmon을 연동하는 것.
==> 여기다 붙여야 Agent가 그걸 받고 Server에 전달함. 이때 View Config를 변경함으로 연동함.
