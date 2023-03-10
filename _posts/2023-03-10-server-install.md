configuration server에 대한 proxy가 있다
많이 사용할 경우 -> configuration server의 복제본을가진 proxy process 를 만들자.
--> configuration proxy server에 접속해서 받아가면된다

<GVP>
RM: sip proxy(아무것도 안하는 비서실장)
mcp: 핵심 프로세스
was: mcp안에 was가 내장되어있음(interpreter가 시나리오를 가져와야 진행될 수 있기 때문에)

-> OCS도 mcp, rm 내장

SIP server: 3300 TCP/ 5060 UDP
RM, MCP: UDP만 지원함

일반적으로 RM을 primary, backup으로 이루어져있지만 primary, primary 로 이루어질 수도 있음
RM, MCP -> connection 줄 필요 없음. 찾아가는 ip 서버 정보만 있으면 된다.
sip server가 rm, mcp가 어디있는지만 알면된다.
--> Config server는 MS가 어디있는지 정보를 가지고 있어야 한다

ms vs mcp
ms: 홀드음악만 내보내기
mcp: 미디어 컨트롤

sip -> mcp 던질 때 스는게 Switches, ms_mcp

Type----
Extension: 상담사 내선정보
VTP: IVR에 사용하는 내선번호
RP: 
VoIP service: mcp로 던져줄 때 쓰는 거
Trunk: PBX끼리 연결시켜주는 것
-> prefix 설정해놓으면 등록된 ip값으로 연결해서 통화

--
EventnetworkReached: trunk 통과

connID가달라서 sip annex 설정,,, 안댐

sip-enable-moh -> true
msml_support -> true
resource_management_by_rm -> true 
--> hold 음악 재생 ok


-------------
Extension vs Voice Treatment Port 
-> IRD에서 전략 사용시 먹히는게 다르다