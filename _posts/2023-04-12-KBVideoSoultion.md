---
layout: post
title: KB Video Soultion
subtitle: project
categories: AICC, daily
tags: [AICC, daily]
---

## Project code  
0079.123  
## MM  
1~1.5 MM  
## Date  
4/17 ~ 5/30  
## Manager  
홍정기 수석님  
## Contact  
KB talk application  
  
# TODO  
4/17: Remote setup & IRD edit  
그 이전에 세현책임님께 환경 셋업 진행도 확인해야함  
  
## TODO2  
Agent Group에 Agent 포함할 것.  
전략에 고객PIN(agent임) 번호 추가  
엑셀에 Agent Group 명은 마음대로 적기  
* ex)화상_통테_부서  
  
IRD에서 기존에 있는 내역 복사-> PIN번호 넣고 -> 검증  
중간에 false인 경우는 원래 복사한 object와 연결하여 잘돌아가는지 검증할 것  
  
-----
# Flow  
PBX: Avaya  
* VDN(Vector Direct Number): alike Routin Point  
* uuid: Avaya의 uu-data를 Genesys가 사용할 수 있는 call-data 형식으로 변환해주는 데 사용됨  
CM에서 RoutingPoint에 Annex값에 전략 넣어서 실행시킬 수도 있음  
  

