---
title   : S-HOOK 3차 데모데이 회고
date    : 2023-08-04 20:46:42 +0900
updated : 2023-08-04 20:47:01 +0900
tags     : 
- 회고
- shook
- 레벨3
- 우테코
---

어느덧 2주 후면 4차 데모데이고, 레벨3가 끝난다.     
S-HOOK 프로젝트를 진행한 후로 시간이 많이 흐른 지금 프로젝트 회고를 작성해보려고 한다.    

## S-HOOK 이란

스플릿의 아이디어로 시작된 S-HOOK은 주제를 보자마자 하고 싶었던 프로젝트였다.   
그때 당시의 서비스 소개는 대략적으로 '킬링파트로 노래를 추천하는 서비스' 라고 적혀있었던 것 같다. 그래서 인공지능을 쓰는 프로젝트일 것 같아 잘 될까? 하는 회의적인 시각도 있었다.    

스플릿은 자신이 도입부만 들어보고 별로라고 생각했던 노래가, 나중에 들었을 때 좋은 노래였다는 것을 알게 된 후에 기획하게 된 서비스라고 했다.      

우리의 서비스, S-HOOK 은 좋아하는 노래의 '킬링파트'를 다른 사람들과 공유할 수 있다. 또한 노래의 가장 좋은 부분인 '킬링파트'를 먼저 들어봄으로써 새로운 노래를 빠르게 탐색할 수 있다.     

### 비하인드

사실 이런 정의를 내릴 수 있게 된 것도 그렇게 오래되지는 않았다 ㅋㅋㅋ    
다들 프로젝트를 해보았다면 알 것이다. 모두가 나와 같은 생각을 하고 있다고 생각하지만 모두가 다 다른 각자의 생각을 갖고 있을 때가 훨씬 많다는 것을.

우리 팀도 동일했다. '이게 이런 기능 아니었어?', '이거 하자고 한 거 아니었어?' 라는 말을 수없이 했다. 수없이 했던 이야기를 반복했고, 수없이 똑같은 문제에 대해 토론했다.      

특히 1차 데모데이, 2차 데모데이 기간까지는 우리도 우리 서비스가 무엇인지 명확하게 정의내리기 어려웠다.     

### 가장 많이 생각했던 페르소나

가장 고민했던 것은 우리 서비스가 제공하고 싶은 가치였다. 

1차 데모데이 때 정했던 첫 페르소나는 다음과 같다.    

```markdown
인디음악 매니아
- 27세 바쁜 직장인
- 인디음악 매니아
- 콘서트 좋아함

Need
- 자신만의 숨은 명곡을 뽐내고 싶다
- 노래 중 자신만의 핵심 파트를 뽐내고 싶다
- 내가 좋아하는 가수의 다른 노래 중 좋은 노래를 찾고 싶다
```

이때 코치분들에게 '주어진 기능에 맞춰서 페르소나를 지정한 것은 아닌가?' 라는 피드백을 받았다. 아무래도 구현하기로 계획했던 기능이 '등록 / 공유', '조회' 였어서 더 그런 것 같다.     
팀 내에서도 그런 의견이 나왔어서, 이후로 페르소나 정립을 다시 해야 했다.     

처음 정했던 아이디어 대로라면 공유에 초점을 둔 서비스가 맞았다. 그렇지만 공유를 통해서 우리가 사용자에게 '줄 수 있는 가치' 는 너무나도 모호했다. 

너무나도 어려운 시간이었지만, 다시 페르소나를 구축했다.    
그렇게 새롭게 만들어진, 2차 데모데이까지의 페르소나는 다음과 같다.     
공유에 초점을 둔 페르소나이다.

```markdown
킬링파트를 등록하고 공유하는 것이 메인인 페르소나

- 내가 좋아하는 부분을 사람들도 좋아한다는 걸 인정받고 싶다.
    - 내가 좋아하는 걸 다른 사람들도 좋아한다고 느낄 때의 인정 (보편적)
        - 사람들이 좋아할 만한 부분을 공유 / 내가 좋아하는 걸 역시 다른 사람들도 좋아하네 → 대중적인 귀
```

이 페르소나를 정할 때, S-HOOK이 공유에 초점을 둔 서비스일까? 추천에 초점을 둔 서비스일까? 를 계속해서 고민했다.     

추천에 초점을 두게 되면 어쩔 수 없이 사용자의 취향을 알아야만 했는데, 현실적으로 우리가 짧은 기간 안에 구현할 수 없는 기능이라 결론 내렸다.     

따라서 공유에 초점을 둔 페르소나를 선정하기로 했고, 그 중에서도 사람들에게 킬링파트를 공유하고, 자신의 음악 취향을 인정받고 싶은 사용자를 타겟으로 한 페르소나를 만들었다.

그러나 이 페르소나에도 하나의 문제점이 있었다.    

해당 페르소나에게 '인정받는 느낌'을 주기 위해 지금까지 높은 득표를 한 킬링파트에 투표를 하게 되면 '축하한다는 메시지'와 '등수'를 띄워주었다. 이를 위해서는 킬링파트의 득표수가 숨겨져야 했고, 결국 킬링파트 투표를 하고 싶지 않은 사용자는 킬링파트를 확인할 수 없게 되었다.    

그렇다. 우리가 줄 수 있는 인정에는 한계가 있었다.     
처음에는 내가 등록한 킬링파트의 순위가 높다면 사용자가 '인정받았다' 라고 생각하지 않을까? 라고 생각했다.    
그러나 그렇게 기능을 제공하게 되면 사용자는 높은 등수의 킬링파트를 계속해서 '찾기만 하는' 등수 퀴즈 서비스 정도로 S-HOOK 을 인지하게 될 것이다. 또한 킬링파트 리스트를 보여주지 않는다면, 킬링파트를 찾기만을 원하는 사용자들을 대거 놓치게 된다. 그것은 우리가 원하는 방향이 아니었다. 

그래서 결국 공유를 통한 '인정'을 주는 것은 제외했다. 2차 데모데이에 구현한 기능들은 '공유' 할 수 있게 하는 기능이었다고 정의하기로 했다.     

그리고 지금, 3차 데모데이 까지의 페르소나는 다음과 같다.     

```markdown
사람들이 많이 소비하는 노래를 찾고 싶은 페르소나

### Needs

- 들어보지 않은 좋은 노래를 찾고 싶다.
- 최근에 사람들이 많이 소비한 노래들 중에서 안 들어본 좋은 노래를 찾고 싶다.

### Goals

- 새로운 노래의 킬링파트들을 들어보며 좋은 노래인지 판단할 수 있었다.
```

킬링파트 소비에 목적을 둔 페르소나이다.     
그렇지만 여전히 순탄하게 정해지지는 않았다...ㅋㅋㅋ

![[third-demoday-persona-1.png]]
![[third-demoday-persona-2.png]]
길었던 3차 데모데이 페르소나 회의의 일부분이다.

3차 데모데이 페르소나를 정하면서도 토론이 오갔다. 이 날은 페르소나에 대한 이야기만 5시간을 했다.     
모두들 우리의 서비스가 제공하고 싶은 가치가 무엇인지 확신하지 못해서 긴 시간을 회의한 것이라 생각한다. 시간은 오래 걸렸지만, 서비스를 위해서는 너무나도 필요한 시간이었다.     

팀원 각자의 의견들을 들어보고, 각 의견들의 모순점을 찾아내고, 모순의 해결점을 찾아내는 회의를 했다.     
어떤 서비스를 만들고 싶은지, 어떤 서비스가 되었으면 좋겠는지, 이 가치를 실현하는 데 있어서 이런 기능들이 필요한 지... 와 관한 이야기를 했다. 그렇게 정해진 페르소나다.

그렇다. 우리가 고민했던 것은 결국 '사용자' 다.

우리는 서비스를 통해 **사용자**에게 어떤 가치를 줄 수 있나?      
우리의 서비스를 통해 **사용자**가 얻어갔으면 하는 것은 무엇인가?     
궁극적으로 우리의 서비스를 통해 **사용자**의 니즈를 달성할 수 있을까?     

라는 질문들에 대답하기 힘겨웠던 날들이 많았다.     

이를 해결하기 위해 했던 회의들은 끝도 없다. 우리 팀은 다른 팀들 사이에서 '회의 많이 하는 팀' 으로 불리고 있었으니까. 오히려 개발보다도 서로의 싱크를 맞추기 위한 회의를 더 많이 했던 것 같다.    

결국 우리가 내린 결론은 이것이다.

우리의 핵심은 유저들이 킬링파트를 만들어 나가며 즐겁게 소비하는 플랫폼을 만드는 것이다.  
그 중에서는 여러 가치가 있는데

- 노래의 킬링파트를 유저들이 만들어 나간다.
- 자신이 등록한 파트를 지인들에게 편하게 제공할 수 있다.
- 유저들이 새로운 노래를 찾는데 킬링파트가 도움이 되도록 한다.

결국 이 가치를 찾기 위해서 멀리 돌아왔고, 그런 과정을 통해 팀원 모두가 인정할 수 있는 서비스와 가치가 만들어졌다고 생각한다.     

무엇보다 기쁜 것은 서비스가 바라보는 것이 기술과 기능이 아니라, '사용자' 라는 것이다.     
그러니 우리는 앞으로 개발을 할 때 '왜 이런 기능을 만들어야 하지?' 라는 의문에 휘둘리지 않을 것이다. 이미 그런 고민들은 6주 동안 했다.     

### 다음으로 제공할 가치는?

이제 기본적으로 '공유'하고, '소비'하는 페르소나에 대한 정의가 완료되었으므로 사용자의 편의를 높여줄 수 있는 가치들을 구상했다.    

```
- 사용자에게 신뢰성 있는 킬링파트를 제공한다.
- 킬링파트를 편리하게 소비할 수 있다.
```

여담이지만, 각 스프린트마다 구현해야 할 '가치'를 잡고 가는 것은 정말 좋은 방법이다.    
팀원들 모두 가치를 반영하는 방향으로 움직일 수 있고, 불필요한 기능들을 쳐낼 수도 있다.     
다들 한 번 시도해보시길.

각각의 가치들을 잘 반영하는 방향으로 마지막 4차 데모데이도 잘 준비하려 한다.     

---
2차 데모데이까지는 기획 지적을 많이 받았는데, 이번에는 기획이 아닌 UX, UI 지적을 받아서 오히려 좋다. 기획은 어느 정도 틀이 잡힌 것 같다. (이제서야)     

브라운이 구현도가 높아서 실제 서비스를 쓰는 것 같다고 해주셔서 너무 기분 좋았다.     
4차 데모데이가 끝나고 만들어질 S-HOOK 이 기대된다.     