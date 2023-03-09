Queue vs Routing Point
아이고,,,아이고,,,,아이고야,,,,,,쪽지시험,,,아이고,,,,,,,,,,,,,,,

Queue : 쌓이는건 EventQueued(CCPulse: CallEntered) / 나가는건 EventDiverted(CCPulse: CallDistributed) / 실패하는건 EventAbandoned

RoutingPoint: EventQueued / EventDiverted
RP는 빠져나갈구멍이 있고 전략이 로딩이 가능해서 선입선출이 아닐지두

전략에 ANY에 자기번호 넣어서 하는경우도있음
차이점은 RP는 옆에 구멍이 있어서 탈출이 가능함, RP는 CTI 전략이 로딩이 가능하지만 Queue는 불가능


-----

13:39:18.897: SIPTR: Received [0,UDP] 502 bytes from 10.1.33.4:5060 <<<<<
REGISTER sip:10.1.14.175:5060;transport=udp SIP/2.0
From: "Genesys Softphone" <sip:7014@10.1.14.175:5060>;tag=1C711677-9543-43E2-A7CB-F3A814E3DDE2-1
To: <sip:7014@10.1.14.175:5060>
Call-ID: 3E6FB390-0EA6-4CB4-BA6A-92D1C2908E2F-1@10.1.33.4
CSeq: 520 REGISTER
Content-Length: 0
Via: SIP/2.0/UDP 10.1.33.4:5060;branch=z9hG4bK115B9E53-A36B-46AE-9DED-8C89B46E8CD5-523
User-Agent: Genesys-Softphone/8.5.400.10 (Windows 10.0.19045)
Max-Forwards: 70
Contact: <sip:7014@10.1.33.4:5060>
Expires: 60

-------
<<<<< : SIP입장 들어오는거
7014@10.1.14.175 : URI
User-Agent: 족적(소프트폰 정보)
Expires 60: 체크하는 시간 60초 그러나 2/3 시간에 체크하러감

------
13:39:18.897: Sending  [0,UDP] 462 bytes to 10.1.33.4:5060 >>>>>
SIP/2.0 200 OK
From: "Genesys Softphone" <sip:7014@10.1.14.175:5060>;tag=1C711677-9543-43E2-A7CB-F3A814E3DDE2-1
To: <sip:7014@10.1.14.175:5060>;tag=0044E04E-33A9-13E4-8A2B-0100007FAA77-278149
Call-ID: 3E6FB390-0EA6-4CB4-BA6A-92D1C2908E2F-1@10.1.33.4
CSeq: 520 REGISTER
Via: SIP/2.0/UDP 10.1.33.4:5060;branch=z9hG4bK115B9E53-A36B-46AE-9DED-8C89B46E8CD5-523;received=10.1.33.4
Contact: <sip:7014@10.1.33.4:5060>;expires=60
Expires: 60
Content-Length: 0
